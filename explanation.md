# Vagrant and Ansible Project README

This project uses Vagrant and Ansible to set up a virtual machine (VM) and deploy a Dockerized application. The project structure includes a Vagrantfile, an Ansible playbook, and two roles. The first role installs Docker and its dependencies, whereas the second role clones the application's Git repository, changes the directory to the root directory, and deploys the application using the `docker-compose up -d` command.

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