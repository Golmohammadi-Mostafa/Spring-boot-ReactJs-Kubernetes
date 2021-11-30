# Spring-boot-ReactJs-Kubernetes


Spring-boot : http://localhost:8080  </br>
Prerequisites: Java 11 / apache-maven-3.6.3

ReactJs : http://localhost:3000

# - Creating Dockerfiles:

1- For Building the Docker image for Frontend go to `stakater-frontend directory` and run the following command:</br>
 a-  `docker build -t stakater-frontend .`

2- For Building the Docker image for Backend go to `stakater-backend directory` and run the following commands:</br>
 a-  `mvn clean install `    
 </br>
 b-  `docker build -t stakater-backend .`

# - Kubernetes deployment file

In the root project directory(Spring-boot-ReactJs-Kubernetes) Execute the command below to deploy the applications to the cluster.<br>

 a- `kubectl apply -f kubernetes`    </br>
 
We can check on the Kubernetes dashboard that the deployment is running with no errors.</br>
Start the Kubernetes dashboard by executing the command `minikube enable dashboard` . </br>

Execute the command below to get a `list of the available services` in the cluster.</br>
`kubectl get services`

Our application is now running successfully in the Kubernetes cluster, but we can’t access it from outside the cluster.</br>
To access our application from outside the cluster, we need to expose the services.</br>

we can see that our service `stakater-backend-service` is running, but the external IP address is `<pending>`. To expose the service, execute that command below.</br>

`minikube service stakater-backend-service`  </br>
`minikube servicestakater-frontend-service`
# `We can now access our application from the URL generated by minikube`
 
 
