## Create User and Dir

```bash
sudo /usr/sbin/useradd jenkins -u 1000
sudo /usr/sbin/usermod -aG docker jenkins

sudo mkdir -p /home1/irteam/jenkins_home
sudo chown -R jenkins:docker /home1/irteam/jenkins_home
```

## Create Docker container

```bash
docker-compose -f docker-compose.yml up -d
```

## custom alias on profile

```bash
// ~/.bash_profile

## alias
export DOCKER_HOME=$HOME/jenkins_home/docker/nginx-jenkins

alias dlogs='cd $DOCKER_HOME;docker-compose logs -f'
alias dps='cd $DOCKER_HOME;docker-compose ps'
alias drestart='cd $DOCKER_HOME;docker-compose restart'
alias dstart='cd $DOCKER_HOME;docker-compose start'
alias dstop='cd $DOCKER_HOME;docker-compose stop'

alias jconn='docker container exec -u 0 -it jenkins bash'
alias nconn='docker container exec -u 0 -it nginx bash'
alias nlogs='docker container logs nginx'  
```



