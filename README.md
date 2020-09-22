# Description

This project contains the manifests required to deploy the [www.carbon.cc](www.carbon.cc) site to a Kubernetes cluster.

# Deployment

```bash
kubectl apply -f www
```

# Notes

## Ingress

The `www.carbon.cc` site is deployed using an `Ingress` which expects linkage to a platform load balancer for external IP resolution.
It is also annotated specifically for use with the NGINX ingress controller running on DigitalOcean to provide hostname resolution for certificate verification, health check configuration, and target rewriting.

## SSL/TLS

The Let's Encrypt service is used as a `ClusterIssuer` and provides certificates specifically for the `www.carbon.cc` domain.
It uses the HTTP verification protocol and assumes access to a public network with proper hostname mapping at the ingress.
