---
icon: server
---

# Kubernetes

## Force kill K8S POD

Whenever you need to kill a POD that does not respond to standard delete command 
you could try to force kill the PODs:

```sh
kubectl -n <namespace> delete pod <pod_name> --force --grace-period=0
```

The `--grace-period=0` need to be provided other way the `--force` option would 
no work.

Source: [https://stackoverflow.com/questions/54478616/how-to-delete-a-pod-in-unknown-state-in-kubernetes](https://stackoverflow.com/questions/54478616/how-to-delete-a-pod-in-unknown-state-in-kubernetes)

## Checking the host resolving on POD

You need to open a terminal in your POD:

```sh
kubectl -n <namespace> exec -it <pod_name> /bin/bash
```

and run the command:

```sh
getent hosts <domain>
```

This should return an IP address if the domain was correctly resolved. If not 
this command returns nothing.

