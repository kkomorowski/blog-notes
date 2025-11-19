---
description: '`jq` and `yq` are the handy tools to parse and manipulate JSON and YAML data'
---

# \`jq\` & \`yq\`

### An example of \`yq\` to extract the names of the services and corresponding addresses from docker-compose file

```
yq eval '(.services | keys[]) as $srv | 
         {$srv: .services[$srv].networks.m2m_network.ipv4_address}' \
   docker-compose-perf.yaml |  
   sed 's/${CI_SUBNET_ID:-0}/0/' |  
   sort -k2
```
