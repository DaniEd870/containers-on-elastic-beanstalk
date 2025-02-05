
# Containers on AWS Elastic Beanstalk

## Overview
This project demonstrates how to use **Docker** and **AWS Elastic Beanstalk** to deploy containerized applications. The project involves creating a custom **Nginx** container image, handling common Docker-related issues, and deploying the container to Elastic Beanstalk.

## What is Docker?
Docker is an open-source platform designed to simplify the process of building, shipping, and running applications. In this project, I created custom images using Docker and deployed them using AWS Elastic Beanstalk.

### Key Benefits of Docker:
- Provides **lightweight** and **portable** containers.
- Simplifies dependency management.
- Enables quick and easy application deployment.

## Understanding Containers and Docker
### Containers
Containers are **lightweight, standalone, and executable** packages that include everything needed to run an application, including:
- Application code
- Runtime
- System libraries
- Configuration files
- Dependencies

A **container image** serves as a **template** for creating running containers.

### Docker Components
- **Docker Desktop**: A tool that simplifies the development and management of Docker containers.
- **Docker Daemon**: A background service that creates, manages, and controls Docker containers.

## Running an Nginx Image
NGINX is a high-performance web server often used as a reverse proxy, load balancer, and caching server. To quickly start an Nginx container, I used the following command:

```sh
docker run -d -p 80:80 nginx
```

## Creating a Custom Image
A **Dockerfile** contains instructions for building a Docker image. My custom Dockerfile does the following:
1. Uses the latest **Nginx** container as a base.
2. Replaces the default Nginx welcome page with a custom `index.html`.

### Building the Custom Image
To build the Docker image from the Dockerfile, I ran:

```sh
docker build .
```

The `.` at the end specifies that Docker should look for the `Dockerfile` in the current directory.

## Running My Custom Image
I encountered an issue when running my custom image because a container was already using **port 80**. The error was resolved by stopping the conflicting container and rerunning the command.

This custom container runs an **Nginx** web server serving my customized **index.html** page.

## Deploying to AWS Elastic Beanstalk
AWS **Elastic Beanstalk** simplifies deploying cloud applications without worrying about the underlying infrastructure.

### Steps to Deploy:
1. **Prepare the Application**
   - Ensure the Docker container is working locally.
2. **Deploy to Elastic Beanstalk**
   - Use the AWS Elastic Beanstalk CLI or AWS Management Console to create an environment.
3. **Monitor Deployment**
   - Track logs and resolve any deployment issues.

### Deployment Time:
Deploying my custom Docker image using **Elastic Beanstalk** took approximately **15 minutes**.

## Key Takeaways
- **Docker containers** provide a portable, efficient way to package applications.
- **Elastic Beanstalk** makes deployment straightforward without handling infrastructure details.
- Debugging **container conflicts** (e.g., port 80 issues) is crucial for smooth deployments.

## Conclusion
This project demonstrated how to use Docker for **containerized application development** and AWS Elastic Beanstalk for **cloud deployment**. The entire process, including setup, debugging, and deployment, provided valuable insights into working with containers in a cloud environment.




Author
Daniella Edem Amenyo-Sedo
AWS Solutions Architect(Candidate) | Cloud & DevOps Enthusiast

