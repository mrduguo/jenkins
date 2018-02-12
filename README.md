# Basic Jenkins with essential plugins  [![Build Status](https://travis-ci.org/mrduguo/jenkins.svg?branch=master)](https://travis-ci.org/mrduguo/jenkins)

## Run for persisted data volume


```bash

mkdir -p ~/jenkins_home

docker pull mrduguo/jenkins

docker run -p 6010:8080 --name jenkins \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v $(which docker):/usr/bin/docker \
   -v ~/jenkins_home:/var/jenkins_home \
  mrduguo/jenkins

# curl -v http://192.168.99.100:6010/job/sandbox-github/build -X POST

```

### Docker hub published tags

https://hub.docker.com/r/mrduguo/jenkins/tags/



## Build


```bash

./gradlew

```

It will build the docker image with latest and versioned tags.


## Run for local testing


```bash

# ./gradlew
docker run -it -p 6010:8080 --rm --name jenkins \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v $(which docker):/usr/bin/docker \
  mrduguo/jenkins

curl -v http://192.168.99.100:6010/job/sandbox-github/build -X POST
docker exec -it mrduguo/jenkins bash


```


* ignore volume mapping if you don't have job to build docker image
* you could access the instance e.g. [http://192.168.99.100:6010](http://192.168.99.100:6010)


