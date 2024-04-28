### Containerization with Docker

- **What is Docker?**
  - **Definition**: Docker is a platform for developing, shipping, and running applications in lightweight, portable containers.
  - **Why Docker?**: It ensures consistency across multiple development and release cycles, standardizing your environment across all stages.

- **Creating Dockerfiles**
  - **Purpose of Dockerfiles**: Dockerfiles are scripts containing a series of commands and instructions to build Docker images.
  - **Steps to Create a Dockerfile**: Learn the basic commands (`FROM`, `RUN`, `COPY`, `EXPOSE`, `CMD`) to script the environment setup.

- **Building and Running Containers**
  - **Building Docker Images**: How to use the Dockerfile to build an image that contains everything your Node.js application needs to run.
  - **Running Containers**: Instructions on how to start a container from a Docker image, including port mapping and volume mounting.

- **Docker Compose**
  - **What is Docker Compose?**: A tool for defining and running multi-container Docker applications.
  - **Using Docker Compose**: Steps to create a `docker-compose.yml` file that orchestrates the configuration of your application services.
  - **Advantages**: Simplifies the management of multi-container applications, making it easy to start, stop, and rebuild services in a coordinated manner.
