# learn-k8s-networking-with-2-tier-app
This repository contains Kubernetes deployment manifests and examples for
deploying a two-tier application on a Kubernetes cluster.

## Table of contents

- Deploying a two-tier application
- Deploying the Backend Pods
- Inspecting the backend deployment
- Exposing the backend pods within the cluster with a Service
- DNS Resolution for the backend service
- Endpoints and Services
- kube-proxy: translating Service IP to Pod IP
- kube-proxy and iptables rules
- Following traffic from a Pod to Service
- Deploying and exposing the frontend Pods
- Exposing the frontend pods
- Load Balancer Service
- Extra hop with kube-proxy and intra-cluster load balancing
- ExternalTrafficPolicy: Local (preserving the source IP)
- Proxy-terminating endpoints in Kubernetes
- How can a Pod's IP address be routable from the load balanc

### Deploying a two-tier application

  **Deploying the backend pods**


```bash 
 kubectl apply -f backend-deployment.yaml
deployment.apps/backend-deployment created

```

Good !

Now, you have a deployment of single pod running the backend API.

verify this:

```bash

kubectl get deployment

```