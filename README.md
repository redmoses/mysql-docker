> I usually keep my files in the location ```~/Workspace```. If you prefer to keep it somewhere else please change the commands accordingly.

## Prerequisites

* Docker
* docker-compose
* make

## Clone the repository
```bash
git clone https://github.com/redmoses/mysql-docker.git ~/Workspace/mysql-docker
```

## Create an alias
Add the below alias in your ```.zshrc``` or ```.bashrc``` file depending on the shell you are using

```bash
alias mysql='cd ~/Workspace/mysql-docker/ && make '
```
Don't forget to load the alias in your environment. You can do so by using the following command
```bash
source ~/.zshrc
```

## Initialize
The first time you use this please run the following command. This command will download mysql docker image if it's not already there. Then it will start it up according to the ```docker-compose.yml``` configuration.
```
mysql up
```

## Available commands
Once you've initialized the docker you can open up your terminal and use the following commands accordingly.

#### Start MySql
```
mysql start
```
#### Stop MySql
```
mysql stop
```
#### Restart MySql
```
mysql restart
```
#### MySql logs
```
mysql logs
```
#### MySql shell
```
mysql shell
```

## Data location
The data will be stored in the location ```~/Workspace/mysql-docker/data```
