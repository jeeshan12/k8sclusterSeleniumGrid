# Selenium Grid using k8s cluster

## Pre-requisite 
Make sure kubectl and miniube is installed on your machine.
- https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/#install-with-homebrew-on-macos
- https://minikube.sigs.k8s.io/docs/start/

After installation is done, run following commands to start minikube 
```sh
minikube start
```

To open dashboard
```sh
minikube dashboard
```

To stop minikube
```sh
minikube stop
```
To expose grid to outside environment i have used ingress. You can also use NodePort for exposing to external environment. 


### Installation guide to configure Ingress
```sh
1. kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.44.0/deploy/static/provider/cloud/deploy.yaml
2. minikube addons enable ingress
```

To disable ingress
```sh
minikube addons disable ingress
```

## Applying deployments

Go to root folder and run the below command
```sh
kubectl apply -f ./
```

To get status of deployemnts, run below command
```sh
kubectl get deployments
```

To get status of service, run below command
```sh
kubectl get services
```

To get status of pods, run below command
```sh
kubectl get pods
```

To get status of pods, run below command
```sh
kubectl get ingress
```

## Tearing down infrastructure
```sh
1. kubectl delete deployment <<deploymentName>>
2. kubectl delete service  <<serviceName>> (Please make sure you should not be deleteing default k8s service)
3. kubectl delete ingress <<ingressName>>
4. minikube addons disable ingress
```
Deployment name , service name , ingressname you can find in yaml file or by running the get commands for deployemnt, service , ingress and pods which are mentioned earlier in same md file.
