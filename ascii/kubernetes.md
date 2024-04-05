# Kubernetes

### Force kill K8S POD <a href="#force_kill_k8s_pod" id="force_kill_k8s_pod"></a>

Whenever you need to kill a POD that does not respond to standard delete command you could try to force kill the PODs:

```
kubectl -n <namespace> delete pod <pod_name> --force --grace-period=0
```

The `--grace-period=0` need to be provided other way the `--force` option would no work.

Source: [https://stackoverflow.com/questions/54478616/how-to-delete-a-pod-in-unknown-state-in-kubernetes](https://stackoverflow.com/questions/54478616/how-to-delete-a-pod-in-unknown-state-in-kubernetes)

### Checking the host resolving on POD <a href="#checking_the_host_resolving_on_pod" id="checking_the_host_resolving_on_pod"></a>

You need to open a terminal in your POD:

```
kubectl -n <namespace> exec -it <pod_name> /bin/bash
```

and run the command:

```
getent hosts <domain>
```

This should return an IP address if the domain was correctly resolved. If not this command returns nothing.

