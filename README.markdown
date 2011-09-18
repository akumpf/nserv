Nserv wants to be a [Heroku](http://www.heroku.com/) / [No.de](https://no.de/) / [AppFog](http://appfog.com/) style service which can be hosted on your own servers. Nserv uses [forever](https://github.com/indexzero/forever) and [node-http-proxy](https://github.com/nodejitsu/node-http-proxy) so is running almost entirely on nodejs.

## Features:
* Easy install in three lines
* Git deployment of applications
* Automatic install of npm modules
* Simple management of deployed applications

## Setup:
Create a fresh ubuntu 10.04 instance, linode or rackspace is good:
[http://library.linode.com/getting-started##sph_deploy-a-linux-distribution](http://library.linode.com/getting-started##sph_deploy-a-linux-distribution)

Setup key pairs:
[http://library.linode.com/security/ssh-keys](http://library.linode.com/security/ssh-keys)

Create ssh config file so you can just "ssh myserver" and get access:
[http://www.karan.org/blog/index.php/2009/08/25/multiple-ssh-private-keys](http://www.karan.org/blog/index.php/2009/08/25/multiple-ssh-private-keys)

Point a domain name to your server or add one to /etc/hosts:
[http://jorgebernal.info/2009/07/17/42foo-virtual-hosts-web-development/](http://jorgebernal.info/2009/07/17/42foo-virtual-hosts-web-development/)

## Server setup (must be root):
`apt-get install curl`  
`curl https://raw.github.com/bradleyg/nserv/master/nserv_server_setup.sh | sh`

## Local setup (linux / osx):
`curl https://raw.github.com/bradleyg/nserv/master/nserv_local_setup.sh | sh`

## Usage (from local machine):

`nserv myserver` where 'myserver' is the ssh hostname
  
This will let you add/delete applications. If adding an application you will be provided with a git remote that you can add to your local repo. Once added execute `git push nserv master` and your server will updated.

## TODO:
* Allow installation as a user other than root
* Use a Procfile to choose the main application file
* Restart servers on machine reboot