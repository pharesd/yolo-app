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

- Apply the MongoDB StatefulSet and Headless Service YAML file using `kubectl apply -f mongo-statefulset.yaml`.

### 3. Deploy Backend Deployment and Service

- Apply the Backend Deployment and Service YAML file using `kubectl apply -f backend-deployment.yaml`.

### 4. Deploy Client Deployment and Service

- Apply the Client Deployment and Service YAML file using `kubectl apply -f client-deployment.yaml`.

### 5. Apply MongoDB Headless Service

- Apply the MongoDB Headless Service YAML file using `kubectl apply -f mongo-headless-service.yaml`.

### 6. Verify Deployment

Use the following commands to verify the deployment:

```bash
kubectl get pods
kubectl get services
```

# Vagrant and Ansible Project README

This project uses Vagrant and Ansible to set up a virtual machine (VM) and deploy a Dockerized microservices application. The project structure includes a Vagrantfile, an Ansible playbook, and roles.

## Prerequisites

Before you begin, ensure you have the following prerequisites installed on your local machine:

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/) (or your preferred virtualization provider)
- [Ansible](https://www.ansible.com/)

## Project Structure

The project directory structure looks like this:

- `Vagrantfile`: Defines the VM setup using Vagrant.
- `playbook.yml`: Ansible playbook for provisioning the VM.
- `roles/`: Directory containing Ansible roles.
    - `install_docker/`: Role for installing Docker and its dependencies.
        - `tasks/main.yml`: Tasks for Docker installation.
    - `git_clone/`: Role for cloning the Git repository.
        - `tasks/main.yml`: Tasks for cloning the Git repository.
    - `create_docker_network/`: Role for creating a Docker network.
        - `tasks/main.yml`: Tasks for creating the Docker network.
    - `create_docker_volume/`: Role for creating a Docker volume.
        - `tasks/main.yml`: Tasks for creating the Docker volume.
    - `database_container/`: Role for creating the database container.
        - `tasks/main.yml`: Tasks for setting up the database container.
    - `backend_container/`: Role for creating the backend application container.
        - `tasks/main.yml`: Tasks for setting up the backend container.
    - `client_container/`: Role for creating the client application container.
        - `tasks/main.yml`: Tasks for setting up the client container.
- `explanation.md`: This documentation file.

## Getting Started

1. **Clone this repository to your local machine:**

   ```bash
   git clone https://github.com/pharesd/yolo.git

2. **Change into the project directory:**
    ```bash
    cd yolo

3. **Start the VM using Vagrant:**
    ```bash
    vagrant up

4. **Stopping the Application:**
    To gracefully stop the application - stop the application and shut down the VM, use the following command:
    ```bash
    vagrant halt

5. **Killing the Application:**
    *Destroy the VM:* To completely destroy the VM and remove all associated resources, including the application, use the following command:
    ```bash
    vagrant destroy -f 

## Accessing the Application
Once the provisioning is complete, you can access your Dockerized application via the VM's IP address or domain name. Be sure to update the IP address or hostname in your application configuration as needed.