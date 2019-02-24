# Docker-Jenkins
Automated builds using jenkins and docker


## Start jenkins master and slave
```
docker-compose up --scale jenkins-slave=2

docker-compose up -d (background)
```

## Build master only
```
docker build -t jenkins-master master/
```

## Build slave only
```
docker build -t jenkins-slave slave/
```

## Scale slaves
```
docker-compose scale jenkins-slave=2
```

References
 - https://jpetazzo.github.io/2015/09/03/do-not-use-docker-in-docker-for-ci/
 - https://github.com/jenkinsci/docker
 

