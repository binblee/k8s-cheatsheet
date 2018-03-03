# Deploy Wordpress to Kubernetes Cluster

## before 1.9.0

### Deploy wordpress and mysql, no PV
```
kubectl create secret generic mysql-pass --from-literal=password=password
kubectl create -f mysql-deployment-1.8.yaml
kubectl create -f wordpress-deployment-1.8.yaml
```

### Get service URL of wordpress

```
$ kubectl get svc
NAME              TYPE           CLUSTER-IP     EXTERNAL-IP     PORT(S)          AGE
wordpress         LoadBalancer   172.21.11.66   x.x.x.x         8080:32120/TCP   7m
wordpress-mysql   ClusterIP      None           <none>          3306/TCP         11m
```



### Access wordpress

```
http://x.x.x.x:8080/
```
## after 1.9.0

```
kubectl create secret generic mysql-pass --from-literal=password=password
kubectl create -f mysql-deployment-1.9.yaml
kubectl create -f wordpress-deployment-1.9.yaml
```



## Reference

[https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/](https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/)