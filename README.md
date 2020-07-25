# onlyoffice-k3s

A kubectl YAML to deploy OnlyOffice on Kubernetes

## Post-Installation

You can tune the prod or dev Kustomize Overlay with :
- onlyoffice-deployment.yaml : to match your storage driver (in my example I use a NFS driver),
- onlyoffice-ingressroute.yaml : to match your FQDN.

## Installation 

```bash
git clone https://github.com/kyzdev/onlyoffice-k3s
cd onlyoffice-k3s
kubectl apply -k overlays/<env>
```
## Uninstallation

```bash
kubectl delete namespace <env>-onlyoffice
```

## Note

The configmap patches a configuration file that is not compatible with Traefik 2.x.
