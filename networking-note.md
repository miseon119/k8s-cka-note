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
