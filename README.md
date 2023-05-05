# Development Environment Deployment : Helm Charts

What are Helm Charts
Helm charts are packages of K8s resources wc are installed into a K8s cluster as a unit. Helm templates, wc make up a chart, separate the definition of a resource, which is largely static, from its configuration, which may differ with each installation.

Why Helm Charts ?
The idea of a helm chart is to template the YAML files so that we can reuse them in multiple environments by dynamically assigning values to them.

Requirements:

* Helm v3.10.1 or later

Add the Helm repositories, so we can access the Kubernetes manifests

```
helm repo add hashicorp https://helm.releases.hashicorp.com
```

## Setup the base Helm Chart

Create the base chart. </br>
This will be the BASE configuration for all deployments.

```
mkdir dev-deployments
cd dev-deployments
helm create api-deployments  
```

Remove all default files in templates folder:

```
 rm -rf templates/*
```

Recreate files in templates folder,</br>
containing only resources you want to templatize as a BASE structure for ALL deployments :

```
configmap.yaml  deployment.yaml  service.yaml
```


## Update the default values.yml (./templates/values.yaml) with base overrides

This deployment uses environment name, replicaCount, resource limits and clusterIP service.


## Validate the Helm Chart

```
helm lint ./api-deployments
```

