---
icon: whale
---

# Docker

### Using the Docker Bridge Gateway IP (Linux)

On Linux, the default Docker bridge network (docker0) typically assigns the host the IP address 172.17.0.1. You can access the host using this address from within a container:

```sh
curl http://172.17.0.1:8080
```
