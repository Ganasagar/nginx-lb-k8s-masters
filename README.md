# Kubernetes Master Load Balancer using a Docker Container 

This is a little wrap on the usual nginx container to setup a simple load balancer for kubernetes api servers.

## Usage

```
# docker run --restart=always -p 6443:16443 ganasagar/nginx-k8s-masterlb <master-1-ip> <master-2-ip> <master-3-ip>
```

Point kubernetes components to `127.0.0.1:16443` or `<ip-of-host:6443>` (and don't forget to mention this in SAN names during cluster setup) and it will be balanced between the three provided IPs. With basic nginx configuration a load balancer stops routing to not responding endpoints, so the components can operate during failure.


