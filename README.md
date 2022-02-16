# Kubernetes Kustomize Tutorial

The content of this folder is base on the
[Simplify Kubernetes YAML with Kustomize](https://youtu.be/5gsHYdiD6v8)
video.

In the production build did NOT sort out the overwriting of `patchesStrategicMerge` vs `patches` order issue.

```bash

kubectl apply -f application/namespace.yaml
kubectl apply -f application/configmap.yaml
kubectl apply -f application/deployment.yaml
kubectl apply -f application/service.yaml

kubectl delete ns example
# withOUT the kustomization.yaml file in the app dir
kubectl apply -f ./application

# basic with kustomize
kubectl apply -k ./application

# overlays with kustomize
kubectl apply -k ./environments/development
kubectl apply -k ./environments/production
```
