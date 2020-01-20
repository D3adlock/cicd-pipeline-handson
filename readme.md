## 1. Install Docker Host

## 2. Instantiate Jenkins

## 3. Create a MultiBranch pipeline



docker network create jenkins

docker pull jenkins:latest
docker run -p 8080:8080 -p 50000:50000 --network jenkins -v /your/home:/var/jenkins_home jenkins


docker build -t 'devenv' . 
docker run -d -P --name devenv --network jenkins --hostname devenv devenv
docker port devenv 22
docker port devenv 8080