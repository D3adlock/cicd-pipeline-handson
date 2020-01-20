## 1. Install Docker Host

https://docs.docker.com/docker-for-mac/install/

## 2. Start and Configure the Jenkins Server

```
# creates the internal docker network
docker network create jenkins

# pull and start the jenkins docker image
docker pull jenkins:latest
docker run -p 8080:8080 -p 50000:50000 -v /Users/cgallarado/dev/nisum/cicd-pipeline-handson-jenkins-home:/var/jenkins_home --network jenkins --hostname jenkins jenkins:latest
```

REPLACE `/Users/cgallarado/dev/nisum/cicd-pipeline-handson-jenkins-home` with your own jenkinshome folder 

## 3. Create the devenv Docker Container

```
docker build -t 'devenv' . 
docker run -d -p 8090:8080 -p 3001:22 --name devenv --network jenkins --hostname devenv devenv:latest
```

## 4. Configure devenv container as docker-slave

## 5. Create a multibranch pipeline for the project

