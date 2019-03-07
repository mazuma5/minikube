# minikube
sudo -i

curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.8.7/bin/linux/amd64/kubectl \
 && chmod +x ./kubectl \
 && sudo mv ./kubectl /usr/local/bin/kubectl


curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.23.0/minikube-linux-amd64 \
  && chmod +x minikube \
  && sudo mv ./minikube /usr/local/bin/minikube


minikube start
kubectl run hello-minikube --image=k8s.gcr.io/echoserver:1.10 --port=8080
kubectl get pod
curl $(minikube service hello-minikube --url)
kubectl delete services hello-minikube
kubectl delete deployment hello-minikube
minikube stop
