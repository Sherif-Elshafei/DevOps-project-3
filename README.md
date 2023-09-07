# DevOps-project-3
Basic Kubernetes infrastructure; deploying a webapp and a mongo-db on a minikube cluster node. 

ng 1 changed file with 0 additions and 15 deletions.
 15 changes: 0 additions & 15 deletions15  
README
@@ -1,15 +0,0 @@
# DevOps-project-3	
## Basic Kubernetes infrastructure	
![Screenshot from 2023-09-07 09-56-50](https://github.com/Sherif-Elshafei/DevOps-project-3/assets/4324447/b94d9fbf-0bf1-455b-b456-5b4da3ccc167)

## Basic interface commands used	
### Install minikube	

### Install Kubectl	
```	
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"	
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"	
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check	
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl	
kubectl version --client	
kubectl version --client --output=yaml	
```
### Start minikube (using docker as driver)
```
minikube start –driver=docker
```
### Deploy configuration files
```
kubectl apply -f mongo-config.yaml 
kubectl apply -f mongo-secret.yaml 
kubectl apply -f mongo.yaml 
kubectl apply -f webapp.yaml
```
### Finding ip of minikube
```
minikube ip
```
or
```
kubectl get node -o wide
```
### Kubectl basic interface commands
```
kubectl get *<all|configmap|secret|pod|service>*

kubectl describe service webapp-service
kubectl logs mongo-deployment-85d45f7888-gjvf4
kubectl logs mongo-deployment-85d45f7888-gjvf4 -f //streamed log
```
