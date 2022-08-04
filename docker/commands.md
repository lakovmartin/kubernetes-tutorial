docker run busybox
docker run -d -p 80:80 docker/getting-started

## docker build -t getting-started .

## docker run -dp 3000:3000 getting-started

## http://localhost:3000. 

src/static/js/app.js file - line 56
## <p className="text-center">No items yet! Add one above!</p>
##  <p className="text-center">You have no todo items yet! Add one above!</p>


docker ps
docker stop
docker rm

docker run -dp 3000:3000 getting-started



docker volume create todo-db

docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started

docker volume inspect
docker inspect getting-started


az group create --name kubernetestutorial --location uksouth

az acr create -n kubernetestutorial -g kubernetestutorial --sku basic --admin-enabled "true"


az aks create `
    --resource-group kubernetestutorial `
    --name kubernetes-tutorial-aks `
    --node-count 1 `
    --generate-ssh-keys `
    --attach-acr kubernetestutorial


az aks install-cli

az aks get-credentials --resource-group kubernetestutorial --name kubernetes-tutorial-aks

kubectl get nodes


docker login kubernetestutorial.azurecr.io --username kubernetestutorial --password N26RZiDoW3hmSW3k3O+IbOwPbpNH9C9M
docker image tag getting-started kubernetestutorial.azurecr.io/getting-started:0.1
docker image push kubernetestutorial.azurecr.io/getting-started:0.1

kubectl apply -f manifest.yaml

kubectl port-forward azure-todo-front-76db9cdc94-8wncz 3000:3000


Scaling replicas
kubectl apply -f manifest-autoscale.yaml
kubectl scale --replicas=3 deployment/azure-todo-front

kubectl get hpa --watch

az aks scale --resource-group myResourceGroup --name myAKSCluster --node-count 3

Updating application