### Notes to setup New Jenkins Agent using Docker

#### Setting up Jenkins Agent using Docker

1. Open `Manage Jenkins` -> `Manage Nodes and Clouds` -> `New Node`
2. Enter the node name as `docker-build-agent` and select `Permanent Agent`
3. Click on `OK`
4. In the `Remote root directory` section, enter the directory path as `/home/jenkins`
5. In the `Labels` section, enter the label as `docker-build-agent`
6. In the `Usage` section, select `Only build jobs with label expressions matching this node`
7. In the `Launch method` section, select `Launch agent by connecting it to the master`
8. Click on `Save`
9. Click on `docker-build-agent` -> `Launch agent`
10. Click on `Build Executor Status` to view the agent status

#### Setting up Docker on Jenkins Agent

1. Open the terminal
2. Run `docker --version` to check if Docker is installed
3. Run `sudo apt-get update`
4. Run `sudo apt-get install apt-transport-https ca-certificates curl software-properties-common`
5. Run `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`
6. Run `sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`
7. Run `sudo apt-get update`
8. Run `apt-cache policy docker-ce`
9. Run `sudo apt-get install docker-ce`
10. Run `sudo systemctl status docker` to check the status of Docker
11. Run `sudo usermod -aG docker jenkins` to add Jenkins user to the Docker group
12. Run `sudo systemctl restart jenkins` to restart Jenkins
13. Run `docker --version` to verify the installation
