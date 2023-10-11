# Project Explanation

## Base Image Selection

In this project, I made careful choices for the base images used in each container to optimize image size and functionality. I utilized Alpine Linux-based images to keep container sizes small, and used official Node.js images for the backend and frontend containers to leverage well-maintained and secure base images.

## Dockerfile Directives

### Backend Container
- In the backend Dockerfile, I used the following directives:
  - `FROM` to select the Node.js 14 image for the build stage.
  - `WORKDIR` to set the working directory.
  - `COPY` to copy package files and source code.
  - `RUN` to install npm dependencies.
  - Another `FROM` to create the final image with a minimal Alpine Linux base.
  - Installation of Node.js runtime in the final image.
  - `COPY --from` to copy the built application from the build stage.
  - Exposing port 5000 and specifying the command to run the server.

### Frontend Container
- Similar to the backend, the frontend Dockerfile includes directives to:
  - Select the Node.js 14 image.
  - Set the working directory.
  - Copy package files and source code.
  - Install npm dependencies.
  - Expose port 3000 and specify the command to run the frontend.

## Docker-Compose Networking

I used Docker Compose to manage the multi-container application. I allocated application ports for the frontend and backend containers, enabling them to communicate. Additionally, I implemented a bridge network to allow containers to communicate with each other using service names as hostnames.

## Docker-Compose Volumes

I defined  a volume in the Docker Compose file to ensure data persistence. This volume is used for database, configuration files, or any data that should survive container restarts.

## Git Workflow

Utilized git branches for feature development for code review and merging. I maintained a clear commit history and used version control best practices.

## Docker Image Tag Naming

I adhered to Docker image tag naming standards for ease of identification. I used semantic versioning to tag the images, providing clear version information for each release.

## DockerHub Screenshot

Here is a screenshot of the deployed images in DockerHub:
![DockerHub image](image.png)

