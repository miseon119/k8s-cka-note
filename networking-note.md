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
