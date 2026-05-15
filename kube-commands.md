____________________________________________________________________________________________________
conex 

connect kubernetes 
kubectl config --kubeconfig=config use-context CONTEXT
kubectl config set-context CONTEXT -> configs individuales

context local= kind-kind

connect kubernetes local 
kubectl config --kubeconfig=config use-context kind-kind

show actual context
kubectl config current-context
___________________________________________________________________________________________________
show api versions all dependencies

kubectl api-resources
___________________________________________________________________________________________________
commands
yamllint -f colored my_archive.yaml -> normaliza archivos yaml

___________________________________________________________________________________________________
SSL

openssl pkey -in MYCRTIFICATE.pem -out tls.key openssl crl2pkcs7 -nocrl -certfile

openssl crl2pkcs7 -nocrl -certfile MYCERTIFICATE.pem | openssl pkcs7 -print_certs -out tls.crt

_____________________________________________________________________________________________________

set a namespace or swap
kubectl config set-context --current --namespace=my-namespace
_________________________________________________________________

Delete and reboot deployment
kubectl rollout restart deployment NAME_deploy -n namespace
___________________________________________________________________

Logs de un container de un deploy
kubectl logs POD_name -c CONTAINER_name -n namespace
_____________________________________________________________________

Exec a un pod y con -c a un container del pod si es q tiene mas de uno 
kubectl exec -it NAME_pod [-c NAME_container] -- /bin/sh

______________________________________________________________________

mostrar mas info del element
kubectl get [element] -o wide 

_______________________________________________________________________

describe un ingress
k -n ingress-anp-resumenes describe ing
______________________________________________________________________
lauch pods

kubectl run my-pod --image=nginx --restart=Never
______________________________________________________________________
launch pod temporal
kubectl run --rm -i --tty test-pod --image=busybox -- /bin/sh
ej:
 # Dentro del pod de prueba, ejecuta:
    wget -qO- http://metrics-server.kube-system.svc.cluster.local:443/metrics

_____________________________________________________________________
export yaml
kubectl get deployment <nombre-del-deployment> -o yaml > <nombre-del-archivo>.yaml

helm upgrade karpenter oci://public.ecr.aws/karpenter/karpenter --version 0.37.3 --namespace "${KARPENTER_NAMESPACE}" --set "settings.clusterName=assistedchannel-stg-eks-new" --set "settings.interruptionQueue=assistedchannel-stg-eks-new" --set "serviceAccount.annotations.eks\.amazonaws\.com/role-arn=arn:aws:iam::596905286713:role/KarpenterNodeRole-assistedchannel-stg-eks-new-us-east-1"
