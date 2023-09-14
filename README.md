# Kaiburr-Task-3
# My Kubernetes Deployment

This project is a simple application deployed on a Kubernetes cluster. It includes a Deployment and a Service for the application, as well as MongoDB deployment with a persistent volume.

## Components
1. My Application - A Node.js app that serves a REST API.
2. MongoDB - Database for the application.
3. Deployment manifests for Kubernetes - YAML files describing the desired state for the application deployment.
4. Service manifests for Kubernetes - YAML files specifying how application communicates to the outside world.


## Prerequisites
1. Docker
2. Minikube or any other Kubernetes platform
3. Helm for MongoDB Setup

## Steps to run the project

**Step 1:** Build the Docker image for the application

Navigate to the application folder and run this command:
docker build -t my_app_image .



**Step 2:** Apply the Kubernetes manifests for application

Enter the following command to apply the Deployment and Service manifests:
kubectl apply -f <Deployment.yaml> kubectl apply -f <Service.yaml>



**Step 3:** Setup MongoDB

Add the Bitnami repository to Helm and install MongoDB:
helm repo add bitnami https://charts.bitnami.com/bitnami helm install my-release bitnami/mongodb



**Step 4:** Apply Persistent Volume Claim for MongoDB

Apply the PVC with following command:
kubectl apply -f <PersistentVolumeClaim.yaml>



**Step 5:** Access the application

Check the services running on your cluster and note down the port assigned to the application:
kubectl get svc



Open a web browser and navigate to `localhost:<NodePort>`

 
