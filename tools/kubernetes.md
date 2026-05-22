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

## Setting the default namespace

```bash
kubectl config set-context <cluster> --namespace <namespace>
```

## Logs from multiple PODs

```bash
kubectl logs -l app.kubernetes.io/name="<app_name>" --all-containers --all-pods
```

## Forwarding ports from k8s cluster

Example:

```bash
kubectl port-forward services/amq 61616:61616 8161:8161
```

You can forward multiple ports, format is `<local_port>:<service_port>`.