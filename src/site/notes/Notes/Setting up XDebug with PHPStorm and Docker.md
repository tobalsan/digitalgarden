---
{"status":"published","project":"[[NoobThink]]","dg-publish":true,"created":"2022-10-06T13:03:00","permalink":"/notes/setting-up-x-debug-with-php-storm-and-docker/","dgPassFrontmatter":true,"updated":"2025-12-15T23:53:53.188+01:00"}
---

# Setting up Xdebug with PHPStorm and Docker

Here's a straight-to-the-meat tutorial on how to use XDebug with PHPStorm when your code lives in a Docker container. **This is for Xdebug version 3**.

## Configure XDebug in your PHP container
You docker container running PHP (`phpfpm` most likely) must be configured to use Docker.
To do so, makes sure that PHP loads the XDebug config file. E.g. for a Debian container and php-fpm 8.0, you must have the file `/etc/php/8.0/fpm/conf.d/20-xdebug.ini`. In this file, put the following config:
```ini
zend_extension=xdebug.so  
  
xdebug.mode=debug   
# default for linux, for mac use "host.docker.internal"  
xdebug.client_host=172.17.0.1  
xdebug.client_port=9003
# Uncomment the line below to have XDebug trigger systematically (on each request or CLI script)
# xdebug.start_with_request=yes
```

Explanation of the parameters:
- `xdebug.mode`: the `debug` value lets you do [step debugging](https://xdebug.org/docs/step_debug).
- `xdebug.client_host`: the IP of the client with which you'll debug (PHPStorm). On mac, use `host.docker.internal`. On Linux, use the host IP, which often is `172.17.0.1` (but you can use `docker network inspect <network_name>` to be sure)
- `xdebug.client_port`: optional, by default it's `9003` but if you have a different configuration you can specify the port here.

Then there's the `xdebug.start_with_request`. If you specify it to `yes`, then XDebug will alwyas trigger PHPStorm, whether you launched a web request or a PHP script. If you use this parameter, you'll have to enable the *Run > Start listening for PHP debug connections* in PHPStorm, but you won't be able to use a specific *Debug configuration*, which I don't really like.
## Configure PHPStorm
Next, head into PHPStorm preferences, and go to **PHP > Servers**. Create a server and configure it like this:
- `Name`: whatever you want
- `Host`: 127.0.0.1
- `Port`: 80
- `Debugger`: Xdebug
- `Use path mappings`: check the box. Since your files reside in a Docker container, you have to indicate to PHPStorm how to find your files
- Then setup your path mappings, mapping your local files to the path they exist in inside your Docker container.
![CleanShot 2022-10-06 at 15.02.29@2x.png](/img/user/Files/CleanShot%202022-10-06%20at%2015.02.29@2x.png)

The last step of configuration is under *Run > Edit configuration*.
Create a `PHP remote debug` configuration:
- `Name`: name it whatever you want (but `Xdebug` sounds fine), 
- Check `Filter debug connection using IDE key`
- `Server`: select the server your created in the previous step
- `IDE key (session id)`: use whatever you want **but remember this value as you'll use it later to trigger the step debugging**.

![CleanShot 2022-10-06 at 15.08.09@2x.png](/img/user/Files/CleanShot%202022-10-06%20at%2015.08.09@2x.png)
Click **OK** to save the settings.

##  Triggering a debug session
Now the configuration is done, all you have to do to start debuggin is to first add a breakpoint in your code. Next, you have several options (all explained on [Xdebug official documentation](https://xdebug.org/docs/step_debug#activate_debugger)):
- When launching a web request
	- You can download a browser extension that will let you enable debugging on the fly
	- Initiate the session by adding a `GET` or `POST` parameter `XDEBUG_SESSION=session_name` (this is where you specify the `IDE key` you specified in PHP Storm debug configuration. For simplicity I used `PHPSTORM`). So if you add `?XDEBUG_SESSION=PHPSTORM` at the end of your URL, it should trigger the debug session.
	- If you want to trigger Xdebug for multiple requests without having to add a parameter to the request each time, use the parameter `XDEBUG_SESSION_START=PHPSTORM` just once. It will set a cookie and trigger the debug session for all subsequent requests. To remove the cookie, use `XDEBUG_SESSION_STOP=PHPSTORM`.
- When using a CLI script
	- Xdebug looks for the `XDEBUG_SESSION` environment variable. So just use: 
	  `export XDEBUG_SESSION=PHPSTORM`
	and you'll be good to go.

---
## Reference
[XDebug - Step debugging](™https://xdebug.org/docs/step_debug)
[PHPStorm - Configure XDebug](https://www.jetbrains.com/help/phpstorm/configuring-xdebug.html)
