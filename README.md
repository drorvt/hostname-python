# hostname-python

The sample application used is a very simple Flask web application; 
Get the application code

### Use dockerhub to clone the repository to your local machine:
1. pull image : docker pull drorvt/hostname-script:latest

### Use git to clone the repository to your local machine:
git@github.com:drorvt/hostname-python.git

###  Change to the app directory:

cd hostname-script

### Create an image

docker build -f docker/Dockerfile -t hostnametaskdror:latest .

### This YAML file is the instructions to Kubernetes for what you want running. It is telling Kubernetes the following:

You want a load-balanced service exposing port 6000
You want four instances of the hostnametask container running
### Use kubectl to send the YAML file to Kubernetes by running the following command:

kubectl apply -f deployment.yaml

### You can see the pods are running if you execute the following command:

kubectl get pods

### Now navigate to http://localhost:6000, and you should see the “This is hostname” message.

curl http://localhost:6000/hostname/
### how to view all hostname in loop 
for i in {1..8};do  curl http://localhost:6000/hostname/ ;echo -e $i\n;done


