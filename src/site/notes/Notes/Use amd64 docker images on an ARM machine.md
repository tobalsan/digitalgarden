---
{"status":"published","project":"[[NoobThink]]","dg-publish":true,"created":"2022-09-17T15:59:00","permalink":"/notes/use-amd64-docker-images-on-an-arm-machine/","dgPassFrontmatter":true,"updated":"2025-12-15T23:52:51.033+01:00"}
---

# Use amd64 docker images on an ARM machine

I was working on a project using a bunch of docker images that were build for amd64 machines, and wanted to run the container on my MacBook with an M1 arm chip.
So when I started the container, they immediately stopped because of a `command` immediately executed at the launch of the container : `/usr/bin/dumb-init`

The error was:
```bash
docker exec /usr/bin/dumb-init: exec format error
```

The problem being that the `dumb-init` binary is an amd64 one, so docker can't run it when on an ARM machine. 

So I started looking for solutions on the internet, and invariably they would consist in rebuilding the docker image using the recent BuildKit with Buildx docker tool, which lets you [build multi-platform images](https://docs.docker.com/build/building/multi-platform/).
Good idea except that I didn't have access to the original Dockerfiles to build the images. Actually, there even wasn't any Dockerfile, the project I was working on uses Ansible to use standard images and update them inside a deployment process. So building the images myself was way too cumbersome.

I first found a [potential solution on Stackoverflow](https://stackoverflow.com/questions/68434301/docker-compose-run-with-specified-platform), thinking that simply adding `platform: "amd64"` to the `docker-compose.yml` services would work, but it didn't.

At the bottom of the page linked above, it is written that you can actually use any type of image when using Docker for Desktop, because it comes shipped with `binfmt_misc`. This was the hint that led me to the solution.
While I didn't install Docker for desktop since I was using docker on a Debian server, I went on the [binfmt_misc docker hub page](https://hub.docker.com/r/tonistiigi/binfmt), and followed the instructions to install it for the docker engine on my Debian server.

Basically all you have to do is run
```bash
docker run --privileged --rm tonistiigi/binfmt --install all
```
or if you want to select which platform to emulate:
```bash
docker run --privileged --rm tonistiigi/binfmt --install amd64,arm64
```
And you're done! 
If you want to check with platform your current docker engine will be able to emulate, simply run
```bash
docker run --privileged --rm tonistiigi/binfmt
```
and it should output something like:
```json
{
  "supported": [
    "linux/arm64",
    "linux/amd64",
    "linux/riscv64",
    "linux/ppc64le",
    "linux/s390x",
    "linux/386",
    "linux/mips64le",
    "linux/mips64",
    "linux/arm/v7",
    "linux/arm/v6"
  ],
  "emulators": [
    "qemu-arm",
    "qemu-i386",
    "qemu-mips64",
    "qemu-mips64el",
    "qemu-ppc64le",
    "qemu-riscv64",
    "qemu-s390x",
    "qemu-x86_64"
  ]
}

```

There's nothing else to do. Once you installed this, just run `docker-compose up` again and watch the magic happen.
