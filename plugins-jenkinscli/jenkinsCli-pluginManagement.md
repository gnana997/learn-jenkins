# Notes on how to manage Jenkins plugins via the CLI

## Install Jenkins CLI on mac

1. Please refer to the above documentation to install Jenkins CLI on mac.

## Jenkins CLI Plugin Management Commands

# Tips:

- use -auth option to provide username and password
- use -noCertificateCheck option to ignore certificate check
- use -restart option to restart Jenkins after installing/enabling/disabling the plugin

1. Run the following command to check the version of the Jenkins CLI:

   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ version
   ```

2. Run the following command to get the help information:

   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ help
   ```

3. Run the following command to install the suggested plugins:

   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ install-plugin <plugin-name>
   ```

4. Run the following command to disable the plugins:

   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ disable-plugin <plugin-name>
   ```

5. Run the following command to list all the installed plugins:

   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ list-plugins
   ```

6. Run the following command to update the plugins:

   ```bash
   java -jar jenkins-cli.jar -s http://localhost:8080/ install-plugin <plugin-name>
   ```

7. Run the following command for restart after disabling the plugin:

```bash
java -jar jenkins-cli.jar -s http://localhost:8080/ safe-restart
```
