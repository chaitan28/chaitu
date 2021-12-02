# Project :Microk8s
## step 1: Install MicroK8s
- MicroK8s will install a minimal, lightweight Kubernetes you can run and use on practically any machine. It can be installed with a snap:
```
sudo snap install microk8s --classic --channel=1.21
```
## step:2 Check the status
- MicroK8s has a built-in command to display its status. During installation you can use the --wait-ready flag to wait for the Kubernetes services to initialise:
```
microk8s status --wait-ready
```
## step:3 Access Kubernetes
- MicroK8s bundles its own version of kubectl for accessing Kubernetes. Use it to run commands to monitor and control your Kubernetes. For example, to view your node:
```
microk8s kubectl get nodes

```
## step:4 Use add-ons
- To start it is recommended to add DNS management to facilitate communication between services. For applications which need storage, the ‘storage’ add-on provides directory space on the host. These are easy to set up:
```
microk8s enable dns storage

```
## step 5: Starting and Stopping MicroK8s
- MicroK8s will continue running until you decide to stop it. You can stop and start MicroK8s with these simple commands:
```
microk8s stop
``` 
- You can start again any time by running:
```
microk8s start
``` 
## Adding worker node 1 to the master
list all the nodes int the cluster , we are not yet attached any worker nodes, it should show only master
``` 
microk8s kubectl get nodes
```
 - commands for adding new nodes to the current microk8s cluster
 ```
  microk8s add-node
```
- command copy it and run it on 1st worker node along with sudo request
```
sudo microk8s join ip:port/xxxxxx
````
