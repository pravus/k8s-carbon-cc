# Description

This project contains the manifests required to deploy the [www.carbon.cc](www.carbon.cc) site to a Kubernetes cluster.

# Deployment

```bash
kubectl apply -f www
```

# Notes

## Ingress

The `www.carbon.cc` site is deployed using an `Ingress` which expects linkage to a platform load balancer for external IP resolution.
It is also annotated specifically for use with the NGINX ingress controller running on DigitalOcean to provide health check configuration and target rewriting.

## SSL/TLS

It is assumed that TLS certificates are handled by the edge lb.
