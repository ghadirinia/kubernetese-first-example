# kubernetese-first-example

>>>>OutPut & command<<<<

commands:
minikube start --driver=virtualbox
kubectl apply -f k8s-configuration/mongo-secret.yaml
kubectl apply -f k8s-configuration/mongo-deployment.yaml
kubectl apply -f k8s-configuration/mongo-service.yaml
kubectl apply -f k8s-configuration/mongo-configmap.yaml
kubectl apply -f k8s-configuration/mongo-express.yaml



command:
kubectl get all

output:
NAME                                            READY   STATUS    RESTARTS   AGE
pod/mongo-deployment-5889fdbb95-5zblx           1/1     Running   0          12m
pod/mongo-express-deployment-7b8c878767-47npt   1/1     Running   0          4s

NAME                            TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
service/kubernetes              ClusterIP      10.96.0.1      <none>        443/TCP          31m
service/mongo-express-service   LoadBalancer   10.109.27.48   <pending>     8081:30009/TCP   4s
service/mongo-service           ClusterIP      10.101.29.61   <none>        27017/TCP        30m

NAME                                       READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/mongo-deployment           1/1     1            1           30m
deployment.apps/mongo-express-deployment   1/1     1            1           4s

NAME                                                  DESIRED   CURRENT   READY   AGE
replicaset.apps/mongo-deployment-5889fdbb95           1         1         1       12m
replicaset.apps/mongo-deployment-666b6bc97c           0         0         0       30m
replicaset.apps/mongo-express-deployment-7b8c878767   1         1         1       4s




command:
minikube service mongo-express-service

output:
|-----------|-----------------------|-------------|-----------------------------|
| NAMESPACE |         NAME          | TARGET PORT |             URL             |
|-----------|-----------------------|-------------|-----------------------------|
| default   | mongo-express-service |        8081 | http://192.168.59.100:30009 |
|-----------|-----------------------|-------------|-----------------------------|
🎉  Opening service default/mongo-express-service in default browser...
marzieh@marzieh-UX310UQK:~$ Opening in existing browser session.

