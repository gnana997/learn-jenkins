# Install Jenkins CLI on mac

1. Download the Jenkins CLI jar file from the Jenkins server using the following command:

   ```bash
    curl -O http://localhost:8080/jnlpJars/jenkins-cli.jar
   ```

2. Run the following command to check the version of the Jenkins CLI:

   ```bash
     java -jar jenkins-cli.jar -s http://localhost:8080/ version
   ```

3. Run the following command to get the initial admin password:

   ```bash
   docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
   ```

4. Run the following command to get the help information:

   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ help
   ```

5. Run the following command to install the suggested plugins:

   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ install-plugin <plugin-name>
   ```

6. Run the following command to create an admin user:

   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ create-user <username> <password>
   ```

7. Run the following command to restart Jenkins:
   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ safe-restart
   ```
