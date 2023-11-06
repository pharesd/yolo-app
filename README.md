# YoloApp Deployment on Kubernetes

This repository contains the configuration files and instructions to deploy the YoloApp application on a Kubernetes cluster. YoloApp is a multi-container application consisting of a MongoDB database, a backend service, and a client application.

## Prerequisites

Before deploying the YoloApp, make sure you have the following prerequisites in place:

- A running Kubernetes cluster.
- `kubectl` CLI tool configured to access your Kubernetes cluster.
- Docker installed to build and push custom Docker images if needed.

## Deployment Steps

Follow the steps below to deploy the YoloApp on your Kubernetes cluster:

### 1. Create Persistent Volumes (Optional)

If you want to use persistent storage for the MongoDB database, create a Persistent Volume (PV) and a Persistent Volume Claim (PVC) by modifying the provided YAML files:

- `mongo-pv.yaml`: Define the Persistent Volume and the Persistent Volume Claim.

Deploy the persistent volume using:
```bash
kubectl apply -f mongo-pv.yaml
```

### 2. Deploy MongoDB StatefulSet and Headless Service

- Apply the MongoDB StatefulSet and Headless Service YAML file using
```bash
 kubectl apply -f mongo-statefulset.yaml
 ```

### 3. Deploy Backend Deployment and Service

- Apply the Backend Deployment and Service YAML file using:
```bash
 kubectl apply -f backend-deployment.yaml
 ```

### 4. Deploy Client Deployment and Service

- Apply the Client Deployment and Service YAML file using:
```bash
 kubectl apply -f client-deployment.yaml
 ```

### 5. Apply MongoDB Headless Service

- Apply the MongoDB Headless Service YAML file using:
```bash
 kubectl apply -f mongo-headless-service.yaml
 ```

### 6. Verify Deployment

Use the following commands to verify the deployment:

```bash
kubectl get pods
kubectl get services
```