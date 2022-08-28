```sh
sadmin@master:~$ kubectl  get pods -n myapp 
NAME                             READY   STATUS    RESTARTS   AGE
my-deployment-556b86c446-j8x28   1/1     Running   0          21m
my-deployment-556b86c446-kp8wz   1/1     Running   0          18m
my-deployment-556b86c446-mg825   1/1     Running   0          18m
my-deployment-556b86c446-pmfjz   1/1     Running   0          18m
my-deployment-556b86c446-xs7bp   1/1     Running   0          18m
sadmin@master:~$ kubectl  get svc -n myapp 
NAME                  TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
my-service            ClusterIP   10.233.3.38     <none>        80/TCP         5h44m
my-service-nodeport   NodePort    10.233.51.142   <none>        80:30000/TCP   61m
sadmin@master:~$ 

```


Доступ до кластера с локальной машины до кластера 
```sh
sasha@T480:~$ hostname
T480
sasha@T480:~$ kubectl --insecure-skip-tls-verify  get nodes
NAME     STATUS   ROLES    AGE    VERSION
master   Ready    master   6d6h   v1.19.3
worker   Ready    <none>   6d6h   v1.19.3
sasha@T480:~$ 
```

- readiness - позволяет установить любую проверку, которая даёт возможность проверять готовность контейнера к приему трафика. Если с приложением что то не так - срабатывает провал пробы.

- liveness - помогают контейнеру понять, когда пришло время для перезапуска. 
