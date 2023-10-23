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
- `ansible/`: Directory containing Ansible-related files.
  - `playbook.yml`: Ansible playbook for provisioning the VM.
  - `roles/`: Directory containing Ansible roles.
    - `docker/`: Role for installing Docker and its dependencies.
      - `tasks/main.yml`: Tasks for Docker installation.
      - `defaults/main.yml`: Role-specific variables (e.g., Docker Compose path).
    - `app/`: Role for deploying the application.
      - `tasks/main.yml`: Tasks for cloning the Git repository and deploying the app.
      - `defaults/main.yml`: Role-specific variables (if needed).
- `README.md`: This documentation file.

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/pharesd/yolo.git

2. **Change into the project directory:**
    ```bash
    cd yolo

3. Start the VM using Vagrant:
    ```bash
    vagrant up


## Accessing the Application
Once the provisioning is complete, you can access your Dockerized application via the VM's IP address or domain name. Be sure to update the IP address or hostname in your application configuration as needed.