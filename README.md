# Docker-Service-Jenkins-Redis #

## System Requirements
 1. Operating System: macOS
 2. Docker Desktop for Mac installed and running

## Introduction

This Docker service integrates Jenkins and Redis, providing a seamless environment for continuous integration (CI) tasks while utilizing Redis for caching and other data storage needs.

Setup Instructions

1. Install Docker Desktop: Ensure that Docker Desktop for Mac is installed and running on your system. You can download Docker Desktop from the official website.

2. Clone the Repository: Clone this repository to your local machine using Git:

```bash
git clone https://github.com/rkshpanigrahi/Docker-Service-Jenkins-Redis.git
``` 

3. Build and Run Docker Containers:
   * Navigate to the cloned repository directory:

   ```bash
   cd Docker-Service-Jenkins-Redis
   ``` 
   * Run the following command to start the Docker containers:
   
   ```bash
   docker-compose up -d
   ``` 
   This command will download the necessary Docker images (if not already downloaded) and start the Jenkins and Redis containers in detached mode.


4. Access Jenkins: Once the containers are up and running, you can access Jenkins by opening a web browser and navigating to http://localhost:8080.
Follow the on-screen instructions to complete the Jenkins setup wizard.
You may need to retrieve the initial administrator password from the Jenkins container. You can do this by running:

```bash
docker-compose exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

5. Configure Jenkins: After unlocking Jenkins, install any necessary plugins and configure Jenkins according to your requirements.
You may want to install additional Jenkins plugins based on your specific CI/CD needs.

6. Redis Configuration (Optional): If you need to configure or interact with Redis, you can do so using a Redis client or by connecting to the Redis container directly.
Redis is accessible on localhost:6379.


7. Monitor the logs of the Jenkins container:

   ```bash
   docker logs -f jenkins-lts
   ```   


8. Connect to Redis from inside the container

   Run the following command to connect inside the Redis container:

   ```bash
   docker exec -it redis sh
   #
   # redis-cli
   127.0.0.1:6379>
   127.0.0.1:6379> set name Rakesh
   OK
   127.0.0.1:6379> get name
   "Rakesh"
   ```

8. stop the containers:

   Run the following command to stop the containers:

   ```bash
   docker-compose down
   ```

