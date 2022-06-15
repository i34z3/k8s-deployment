# k8s zero to production

kind create cluster --name=esquenta

kubectl cluster-info --context kind-esquenta

kubectl get nodes

# create pod

kubectl apply -f pod/nginx.yaml

kubectl get po

kubectl port-forward pod/nginx 9090:80

curl http://localhost:9090

kubectl delete pod nginx

# create replicaset

kubectl apply -f replicaset/nginx-rs.yaml

kubectl get po

kubectl delete pod nginx-id

kubectl get po

# create deployment (versions)

kubectl apply -f src/deployment/nginx-deployment.yaml

kubectl get po

# run app go

go run main.go