> I usually keep my files in this location ```~/Workspace```. If you prefer to keep it somewhere else please change the commands accordingly.

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
alias mysql='cd ~/Workspace/mysql/ && make '
```
## Controlling mysql docker
