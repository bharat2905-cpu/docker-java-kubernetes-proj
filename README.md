# docker-java-kubernetes-proj# 
Deploying Java Applications with Docker and Kubernetes

# Install Maven for java applications
## step 1.
$ sudo apt install maven
$ mvn --version
$ export MAVEN_HOME=/usr/share/maven
$ echo $MAVEN_HOME

## step 2.
### Build the docker image
$ docker images
$ mvn clean install
$ docker build -t bharat2002/productcatalogue:latest .

$ mvn clean install
$ docker build -t bharat2002/stockmanager:latest .

$ mvn clean install
$ docker build -t bharat2002/shopfront:latest .

$ docker login -u <dockerhub_username>
### docker images push on DockerHub
$ docker push bharat2002/productcatalogue:latest
$ docker push bharat2002/stockmanager:latest
$ docker push bharat2002/shopfront:latest

## step 3.
### apply service.yaml
$ kubectl apply -f shopfront-service.yaml
$ kubectl apply -f productcatalogue-service.yaml
$ kubectl apply -f stockmanager-service.yaml
$ kubectl get pod
$ kubectl get deployment
$ kubectl get svc

## step 4.
# Get IP address our website
$ minikube service shopfront  # this is frontpage
	  URL TO SEARCH:- http://192.168.*.*:*****
$ minikube service productcatalogue # this is product data
	  URL TO SEARCH:- http://192.168.*.*:*****/products
$ minikube service stockmanager # this is stock data
	  URL TO SEARCH:- http://192.168.*.*:*****/stocks
