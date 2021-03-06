# Deploy UNIFI controller in kubernetes

## Description
This replository contains Yaml Files to deploy UNIFI controller in Kubernetes cluster.
This repository uses Stateful Set object to manage persistent volume.

## Requirements
This deployment requires following configuration:
- kubernetes cluster. This was tested in [Microk8s](https://github.com/stanislaspiron/microk8s_awx/blob/main/microk8s/microk8s_install.md)
- nfs [storage class](https://github.com/stanislaspiron/microk8s_awx/blob/main/nfs/README.md)
- [metallb](https://github.com/stanislaspiron/microk8s_awx/blob/main/microk8s/install_metallb.md) load balancer

## Install 
Update the service file with expected Metallb IP address.


**Create the deployment**
```
kubectl apply -f unifi-statefulset.yml
```


Source : https://flores.eken.nl/running-unifi-controller-on-k8s/


To adopt an AP, connect the APM with user : ubnt / password : ubnt 

and execute following command:

```
set-inform http://192.168.1.200:8080/inform
