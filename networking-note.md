# Networking Note

## Common Questions

What is the CNI plugin configured to be used on this kubernetes cluster?
```bash
ls /etc/cni/net.d/
```

What binary executable file will be run by kubelet after a container and its associated namespace are created.
```bash
cat /etc/cni/net.d/10-flannel.conflis
```
check `type` key's value

Changing the IP in my Kubernetes cluster?

check my IP
```bash
ip a | grep eth0
```

we need to change the default IP address by adding
```bash
kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')&env.IPALLOC_RANGE=10.50.0.0/16"
kubectl get pods -n kube-system
```

Identify the name of the bridge network/interface created by weave on each node?
```
weave
```
What is the POD IP address range configured by weave?
```bash
 ip addr show weave
```

What network range are the nodes in the cluster part of?
```bash
apt update
apt install ipcalc
ip a | grep eth0 
ipcalc -b 10.2.37.12/24
```

### What is the range of IP addresses configured for PODs on this cluster?
```bash
kubectl logs <weave-pod-name> weave -n kube-system
```

### What is the IP Range configured for the services within the cluster?
```bash
cat /etc/kubernetes/manifests/kube-apiserver.yaml | grep cluster-ip-range
```

### What type of proxy is the kube-proxy configured to use?
```bash
kubectl logs <kube-proxy-pod-name> -n kube-system
```
