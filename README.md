MySQL + PHPMYADMIN
==================

> I usually keep my files in the location `~/Workspace`. If you prefer to keep it somewhere else please change the commands accordingly.

## Prerequisites
The links for the installation guides are given along with the prerequisites
* Docker
  * [Mac](https://download.docker.com/mac/beta/Docker.dmg)
  * [Linux](https://docs.docker.com/engine/installation/linux/)
  * [Windows](https://download.docker.com/win/beta/InstallDocker.msi)
* [docker-compose](https://docs.docker.com/compose/install/)
* make
  * [Mac](http://stackoverflow.com/a/11494872/2894655)
  * [Linux](http://www.cyberciti.biz/faq/debian-linux-install-gnu-gcc-compiler/)
  * [Windows](http://gnuwin32.sourceforge.net/packages/make.htm)

## Clone the repository
```bash
$ git clone https://github.com/redmoses/mysql-docker.git ~/Workspace/mysql-docker
```

## Create an alias
Add the following line in your `.zshrc` or `.bashrc` file depending on the shell you are using

```bash
alias mysql='make -C ~/Workspace/mysql-docker/ '
```
Don't forget to load the alias in your environment. You can do so by using the following command
```bash
$ source ~/.zshrc
```

## Initialize
The first time you start your mysql docker you have to run the following command. This command will download mysql docker image if it's not already there. Then it will start it up according to the `docker-compose.yml` configuration.
```
$ mysql up
```

## Available commands
Once you've initialized the docker you can open up your terminal and use the following commands accordingly.

#### Start MySql
Start up the mysql container
```
$ mysql start
```
#### Stop MySql
Stop the mysql container
```
$ mysql stop
```
#### Restart MySql
Restart the mysql container
```
$ mysql restart
```
#### MySql logs
Show the logs of the running container
```
$ mysql logs
```
#### MySql shell
To connect to mysql shell
```
$ mysql shell
```

## Data location
The data will be stored in the location `~/Workspace/mysql-docker/data`

## MySql configurations

To edit your configurations you can open up `docker-compose.yml` and change the environment variables accordingly.
* `MYSQL_ROOT_PASSWORD` The root password of your database server
* `MYSQL_DATABASE` The name of the default database to start the container with. You can ignore this if you don't want the server to start with an already created database.
* `MYSQL_USER` If you've created a default database then the user defined here will have all permissions over that database.
* `MYSQL_PASSWORD` The default user's password

If you want to have custom mysql settings you can edit the file `config/custom.cnf` according to your needs.

You can learn more about this image from [here](https://hub.docker.com/_/mysql/).

## Refreshing the database
If you want to start fresh and delete all old data you can do the following -
```bash
$ mysql down && sudo rm -rf ~/Workspace/mysql-docker/data && mysql up
```
