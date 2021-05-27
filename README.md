# Deploy UNIFI controller in kubernetes

Before deploying UNFI Controller:
- create a nfs [storage class](https://github.com/stanislaspiron/microk8s_awx/blob/main/nfs/README.md)
- Install [metallb](https://github.com/stanislaspiron/microk8s_awx/blob/main/microk8s/install_metallb.md)

**Create the deployment**
```
kubectl apply -f 01-deployment.yml
```


**Create the Persistent Volume Claim**
```
kubectl apply -f pvc.yml
```

**Create the service**
```
kubectl apply -f service.yml
```

Source : https://flores.eken.nl/running-unifi-controller-on-k8s/


To adopt an AP, connect the APM with user : ubnt / password : ubnt 

and execute following command:

```
set-inform http://192.168.1.200:8080/inform
