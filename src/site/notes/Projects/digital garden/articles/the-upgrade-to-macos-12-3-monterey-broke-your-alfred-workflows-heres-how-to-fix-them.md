---
{"title":"Alfred workflows broken in macOS 12.3 Monterey? Here's how to fix them","slug":"the-upgrade-to-macos-12-3-monterey-broke-your-alfred-workflows-heres-how-to-fix-them","created":"2023-06-06T04:54:17.000Z","updated":"2024-12-07T22:10:40.004+01:00","dg-publish":true,"dg-list-home":true,"project":["[[noobthink.com]]"],"permalink":"/projects/digital-garden/articles/the-upgrade-to-macos-12-3-monterey-broke-your-alfred-workflows-heres-how-to-fix-them/","dgPassFrontmatter":true}
---

# Alfred workflows broken in macOS 12.3 Monterey? Here's how to fix them
> [!info] This article is obsolete
> This is a relatively old post, written in 2022 but published in 2023. It could still be helpful to some people who didn't update to macOS Ventura yet.

Many Alfred workflows rely on Python 2, but in the most recent upgrade of macOS (at the time of writing this article), namely macOS 12.3 Monterey, Apple decided to ditch the bundled version 2 of Python. As a consequence, you might have Alfred workflows that simply stopped working.

Thankfully, it should be fairly easy to get them working again, in two steps.

## Install back Python 2.7 using [homebrew](https://brew.sh/)

```shell
brew update
brew install pyenv
```

Configure your shell to use `pyenv`. See [https://github.com/pyenv/pyenv#set-up-your-shell-environment-for-pyenv](https://github.com/pyenv/pyenv#set-up-your-shell-environment-for-pyenv) for details. Here is how to do it with Zsh:

```shell
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```

You will need to relaunch your terminal session in order to use pyenv (quit your terminal app or run `exec "$SHELL"`.

Now you can install Python 2.7, and create a symlink to it in `/usr/local/bin`:

```shell
pyenv install pypy2.7-7.3.6

// Create the symlink so Workflows find it
ln -s ~/.pyenv/versions/pypy2.7-7.3.6/bin/python /usr/local/bin/python
```

## Update your workflows

Now, head up to [this list of Alfred Workflows updated for macOS Monterey 12.3](https://github.com/alfredapp/updated-third-party-python2-workflows), and download the workflows that are currently broken. Double click on the downloaded items, and it should open Alfred automatically and prompt you to upgrade the workflows.

Once upgraded, your workflows should start working again.

Sources:
[Alfred MacOS 12.3 Python2 PHP Command not found error](https://www.alfredforum.com/topic/18128-alfred-macos-123-python2-php-command-not-found-error/)
[Making Python 2 Workflows work on macOS Monterey 12.3 and above](https://www.alfredforum.com/topic/17941-making-python-2-workflows-work-on-macos-monterey-123-and-above/)
[Python 2 and macOS Monterey](https://www.alfredapp.com/help/kb/python-2-monterey/)
[Convert updated workflow README](https://github.com/willemml/alfred-convert#macos-123-and-later)
