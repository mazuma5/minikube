# Minikube
sudo -i

curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \
chmod +x minikube \
mv ./minikube /usr/bin/minikube 


curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl \
chmod +x ./kubectl \
mv ./kubectl /usr/bin/kubectl 


minikube start --vm-driver=none 

kubectl run hello-minikube --image=k8s.gcr.io/echoserver:1.10 --port=8080 \ 
kubectl expose deployment hello-minikube --type=NodePort \  (deployement is creating pod/pod is nothing but executables)
curl $(minikube service hello-minikube --url) \  (Expose as service)
kubectl get pod 

kubectl get nodes \
curl $(minikube service hello-minikube --url) \
kubectl delete services hello-minikube \
kubectl delete deployment hello-minikube \
minikube stop 


minikube delete \
rm -rf ~/.minikube
