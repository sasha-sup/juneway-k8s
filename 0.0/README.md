```sh
sadmin@master:~$ grep DESCRIPTION /etc/*release
/etc/lsb-release:DISTRIB_DESCRIPTION="Ubuntu 20.04.4 LTS"
sadmin@master:~$ kubectl get pods -A -o wide
NAMESPACE       NAME                                       READY   STATUS    RESTARTS   AGE    IP             NODE     NOMINATED NODE   READINESS GATES
cert-manager    cert-manager-86548b886-8ppwm               1/1     Running   0          129m   10.233.94.3    worker   <none>           <none>
cert-manager    cert-manager-cainjector-6d59c8d4f7-66qlc   1/1     Running   0          129m   10.233.94.2    worker   <none>           <none>
cert-manager    cert-manager-webhook-578954cdd-mqdk2       1/1     Running   0          129m   10.233.94.4    worker   <none>           <none>
ingress-nginx   ingress-nginx-controller-bzcxp             1/1     Running   0          130m   10.233.94.1    worker   <none>           <none>
kube-system     calico-kube-controllers-7fbf9b4bbb-btqck   1/1     Running   0          130m   192.168.0.17   worker   <none>           <none>
kube-system     calico-node-h2mgr                          1/1     Running   0          130m   192.168.0.27   master   <none>           <none>
kube-system     calico-node-klg96                          1/1     Running   0          130m   192.168.0.17   worker   <none>           <none>
kube-system     coredns-7677f9bb54-c9gp4                   1/1     Running   0          129m   10.233.70.1    master   <none>           <none>
kube-system     coredns-7677f9bb54-cddpt                   1/1     Running   0          129m   10.233.94.5    worker   <none>           <none>
kube-system     dns-autoscaler-5b7b5c9b6f-mlfjt            1/1     Running   0          129m   10.233.70.2    master   <none>           <none>
kube-system     kube-apiserver-master                      1/1     Running   0          131m   192.168.0.27   master   <none>           <none>
kube-system     kube-controller-manager-master             1/1     Running   0          131m   192.168.0.27   master   <none>           <none>
kube-system     kube-proxy-j7dns                           1/1     Running   0          130m   192.168.0.27   master   <none>           <none>
kube-system     kube-proxy-p82sc                           1/1     Running   0          130m   192.168.0.17   worker   <none>           <none>
kube-system     kube-scheduler-master                      1/1     Running   1          131m   192.168.0.27   master   <none>           <none>
kube-system     nginx-proxy-worker                         1/1     Running   0          130m   192.168.0.17   worker   <none>           <none>
kube-system     nodelocaldns-dg2rm                         1/1     Running   0          129m   192.168.0.17   worker   <none>           <none>
kube-system     nodelocaldns-n7vff                         1/1     Running   0          129m   192.168.0.27   master   <none>           <none>
sadmin@master:~$ kubectl get pods -n ingress-nginx -o wide
NAME                             READY   STATUS    RESTARTS   AGE    IP            NODE     NOMINATED NODE   READINESS GATES
ingress-nginx-controller-bzcxp   1/1     Running   0          130m   10.233.94.1   worker   <none>           <none>
sadmin@master:~$ systemctl status kubelet.service 
● kubelet.service - Kubernetes Kubelet Server
     Loaded: loaded (/etc/systemd/system/kubelet.service; enabled; vendor preset: enabled)
     Active: active (running) since Wed 2022-08-17 10:33:04 UTC; 2h 13min ago
       Docs: https://github.com/GoogleCloudPlatform/kubernetes
   Main PID: 17737 (kubelet)
      Tasks: 0 (limit: 4648)
     Memory: 29.7M
     CGroup: /system.slice/kubelet.service
             └─17737 /usr/local/bin/kubelet --logtostderr=true --v=2 --node-ip=192.168.0.27 --hostname-override=master --bootstrap-kubeconfig=/etc/kubernetes/bootstrap-kubelet.conf --config=/etc/kubernetes/kube>
sadmin@master:~$ 
```