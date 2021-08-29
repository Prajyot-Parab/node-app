# Minimal Node.js Hello World example

This repo contains a minimal hello world application written in Node. This repo will document the many ways you can deploy this application.

## Run locally

```bash
npm install
npm start
```

## Run in a container

```bash
docker build -t node-hello-world:latest .
docker run -it -p 8080:8080 --name node-hello-world node-hello-world:latest
```

## Run on Kubernetes Cluster

Ensure the container image URL is updated in [deployment.yaml](config/deployment.yaml).

```bash
kubectl config current-context
kubectl apply -f k8s/
kubectl rollout status deployment/node-hello-world
kubectl get services -o wide
```
