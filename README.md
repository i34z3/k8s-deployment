# k8s zero to production

kind create cluster --name=esquenta

kubectl cluster-info --context kind-esquenta

kubectl get nodes

# create pod

kubectl apply -f pod/nginx.yaml

kubectl get po

kubectl port-forward pod/nginx 9090:80

curl http://localhost:9090

# delete pod

kubectl delete pod nginx

# create replicaset (undeleted pod)

kubectl apply -f replicaset/nginx-rs.yaml

kubectl get po
NAME          READY   STATUS    RESTARTS   AGE
nginx-9hlzb   1/1     Running   0          69s

kubectl delete pod nginx-9hlzb

kubectl delete pod nginx-9hlzb 
pod "nginx-9hlzb" deleted

kubectl get po
NAME          READY   STATUS    RESTARTS   AGE
nginx-qzvs9   1/1     Running   0          5s
