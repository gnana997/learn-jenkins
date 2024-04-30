# Follow the steps below to run jenkins locally using docker.

1. Build Steps:

   1. Clone the repository.
   2. Run the following command to build the docker image:
      ```bash
      docker build -t jenkins .
      ```

2. Run Steps:
   1. Create network and volumes:
      ```bash
      docker network create --subnet=172.20.0.0/16 jenkins
      docker volume create jenkins-data
      docker volume create jenkins-docker-certs
      ```
   2. Run the following command to run the docker container:
      ```bash
      docker run --name jenkins-blueocean --restart=on-failure --detach \
        --network jenkins --env DOCKER_HOST=tcp://docker:2376 \
        --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=1 \
        --publish 8080:8080 --publish 50000:50000 \
        --volume jenkins-data:/var/jenkins_home \
        --volume jenkins-docker-certs:/certs/client:ro \
        jenkins
      ```
   3. Open the browser and navigate to `http://localhost:8080/` to access the Jenkins dashboard.
   4. Run the following command to get the initial admin password:
      ```bash
      docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
      ```
   5. Copy the password and paste it in the Jenkins dashboard to unlock it.
   6. Install the suggested plugins.
   7. Create an admin user.
   8. Click on `Save and Finish`.
   9. Click on `Start using Jenkins`.
