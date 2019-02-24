# Docker-Jenkins
Automated builds using jenkins and docker


## Start jenkins master and slave
```
docker-compose up

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
