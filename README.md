# django-todo
A simple todo app built with django

# Tools Used:
1)git 2) AWS-EC2 3) Docker 4)Minikube
# What we Learn in this:

1)Build Kubernetes cluster on AWS from scratch with minikube

2)Setup and manage docker containers for django and react

3)Managed Deployment , Replication, Auto-healing, Auto-Scaling for kubernetes cluster

4)Managed network and services with host IP Allocation

# Step 1: Install Docker and Minikube

sudo apt-get update

sudo apt install docker.io

# Step 2: Build image using docker file and Push image in docker hub and use that one in this project for kubernetes 

# Step 3: Install minikube using link or install using below cmd:https://minikube.sigs.k8s.io/docs/start/

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

sudo install minikube-linux-amd64 /usr/local/bin/minikube

* The "docker" driver should not be used with root privileges. If you wish to continue as root, use --force.
* 
* If you are running minikube within a VM, consider using --driver=none:

minikube status

minikube start --force   ... if as root user

# Step 4: Install Kubectl

sudo snap install kubectl --classic

kubectl get po -A


# Step 5: Go inside k8s folder and run below cmds

/home/ubuntu/django-todo-cicd/k8s

kubectl apply -f pod.yaml

kubectl get pods

kubectl apply -f deployment.yaml

kubectl get deployment

kubectl get rs

kubectl apply -f service.yaml

kubectl get svc

minikube service todo-service --url

curl -L your-url      -> example curl -L http://192.168.49.2:30007 

# Step 6: for Host IP Allocation:

sudo vim /etc/hosts

paste like this

192.168.49.2 rushiapp.com

Now we can serach rushiapp.com on command line interface for testing purpose
