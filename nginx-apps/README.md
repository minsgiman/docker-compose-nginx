## Create Docker container

```bash
// ./nginx-apps
docker-compose up -d
```

### Check container status

```bash
docker-compose ps
# or
docker ps -a
```

### Check container logs

```bash
docker-compose logs
# or
docker container logs nginx
```

### Stop Container

```bash
docker-compose stop
# or
docker container stop nginx
```

### Start Container

```bash
docker-compose start
# or
docker container start nginx
```

### Connect to Container

```bash
docker container exec -u 0 -it nginx bash
```

## custom alias on profile

```bash
// ~/.bash_profile
  
## alias
export DOCKER_HOME=$HOME/jenkins_home/docker/nginx-apps

alias dlogs='cd $DOCKER_HOME;docker-compose logs -f'
alias dps='cd $DOCKER_HOME;docker-compose ps'
alias drestart='cd $DOCKER_HOME;docker-compose restart'
alias dstart='cd $DOCKER_HOME;docker-compose start'
alias dstop='cd $DOCKER_HOME;docker-compose stop'

alias nconn='docker container exec -u 0 -it nginx bash'
alias nlogs='docker container logs nginx'
```
