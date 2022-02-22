# <img src="logo.png" alt="vs code logo" width="60" /> myBalenaCodeServer

myBalenaCodeServer is a free Visual Studio Code based IDE that runs in your browser, served from your Raspberry Pi!

* Forked from [balenaCodeServer](https://github.com/SamEureka/balenaCodeServer), for personal use, to meet my development needs.

* Based on the [linuxserver.io](https://github.com/linuxserver/docker-code-server) code-server Docker image.

* Includes the following mods:
  
  * [DotNet Mod](https://github.com/linuxserver/docker-mods/tree/code-server-dotnet) for .NET development.
  * [Golang Mod](https://github.com/linuxserver/docker-mods/tree/code-server-golang) for Golang development.
  * [Python3 Mod](https://github.com/linuxserver/docker-mods/tree/code-server-python3) for Python development.

---

### Equipment Needed
* Raspberry Pi (tested on Pi4)
---
### Install
Running this project is as simple as deploying it to a balenaCloud application. You can deploy it in one click by using the button below:

[![balena deploy button](https://www.balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/javiercp/balenaCodeServer)

---
### Using myBalenaCodeServer

* Type `<device-ip>:8080` in a browser window _(You can find your device IP address in the Balena Console)_
* The default password for servers deployed with the balena deploy button is `b@13n4!` 
* The default sudo password is `b@13n4!sudo`
* else the password for both is `password`

* The GitHub and Balena CLIs are pre-installed. Authentication instructions [here](gh_balena_auth.md).
 
* If you get a node version warning when using the balena-cli, installing NVM and a supported version of Node will get rid of the warning. Here are some quick [install instructions](nvm_install.md)  

---
### Device Variables
|Env Variable / Default Value|Function|
|---|---|
|PORT=8080|code-server port. Default is 8080. 
|PUID=1000|for UserID|
|PGID=1000|for GroupID|
|SHELL=/usr/bin/zsh|Sets the default terminal shell to ZSH. To use BASH change to '/bin/bash'
|TZ=Europe/London| Specify a timezone to use EG Europe/London, America/Los_Angeles|
|PASSWORD=password|Optional web gui password, if PASSWORD or HASHED_PASSWORD is not provided, there will be no auth.|
|HASHED_PASSWORD=|Optional web gui password, overrides PASSWORD, instructions on how to create it is below.|
|SUDO_PASSWORD=password|If this optional variable is set, user will have sudo access in the code-server terminal with the specified password.|
|SUDO_PASSWORD_HASH=|Optionally set sudo password via hash (takes priority over SUDO_PASSWORD var). Format is $type$salt$hashed.|
|PROXY_DOMAIN=code-server.my.domain|If this optional variable is set, this domain will be proxied for subdomain proxying.|
|DEFAULT_WORKSPACE=/config/workspace|If this optional variable is set, code-server will open this directory by default|