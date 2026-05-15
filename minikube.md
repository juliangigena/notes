init a cluster -> minikube start [-p nameCluster] [--kuberntes-version=vX.XX.X] => minikube start -p minikube2 --kubernetes-version=v1.24.0

list all cluster initzialized -> minikube profile list

update context de k8s -> minikube update-context [-p minikube2] 

Actual kubeconfig de k8s-> kubectl config current-context

status cluster -> minikube status [-p nameCluster] 

stop cluster -> minikube cluster [-p nameCluster] 

show images loaded into minikube cluster -> minikube -p minikube2 ssh -- docker images 

load an inage into the cluster -> minikube [-p minikube2] image load nameImages:tag

