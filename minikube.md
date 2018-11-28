#####  kubectl --context=minikube run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 --port=9090

######  kubectl --context=minikube expose deployment hello-minikube --type=NodePort

```
~/kubernetes-complete-guide(master ✔) kubectl --context=minikube get all --all-namespaces
NAMESPACE     NAME                                  READY     STATUS    RESTARTS   AGE
default       pod/hello-minikube-1115430580-hw0jq   1/1       Running   0          34m
kube-system   pod/kube-addon-manager-minikube       1/1       Running   0          8h
kube-system   pod/kube-dns-196007617-htmnj          3/3       Running   0          8h
kube-system   pod/kubernetes-dashboard-b16pb        1/1       Running   0          8h

NAMESPACE     NAME                                         DESIRED   CURRENT   READY     AGE
kube-system   replicationcontroller/kubernetes-dashboard   1         1         1         8h

NAMESPACE     NAME                           TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)          AGE
default       service/hello-minikube         NodePort    10.0.0.87    <none>        9090:30524/TCP   8m
default       service/kubernetes             ClusterIP   10.0.0.1     <none>        443/TCP          8h
kube-system   service/kube-dns               ClusterIP   10.0.0.10    <none>        53/UDP,53/TCP    8h
kube-system   service/kubernetes-dashboard   NodePort    10.0.0.120   <none>        80:30000/TCP     8h

NAMESPACE     NAME                                   DESIRED   CURRENT   UP-TO-DATE   AVAILABLE   AGE
default       deployment.extensions/hello-minikube   1         1         1            1           34m
kube-system   deployment.extensions/kube-dns         1         1         1            1           8h

NAMESPACE     NAME                                              DESIRED   CURRENT   READY     AGE
default       replicaset.extensions/hello-minikube-1115430580   1         1         1         34m
kube-system   replicaset.extensions/kube-dns-196007617          1         1         1         8h
~/kubernetes-complete-guide(master ✔)
```

##### minikube service hello-minikube --url


