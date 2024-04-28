### Notes to setup a new Jenkins Agent in Jenkins

#### Setting up Jenkins Agent using Azure Ubuntu VM

1. Open Azure Portal
2. Click on `Create a resource`
3. Search for `Ubuntu Server 18.04 LTS`
4. Click on `Create`
5. Enter the details and click on `Review + create`
6. Click on `Create`
7. Wait for the deployment to complete
8. Click on `Go to resource`
9. Copy the `Public IP address`
10. Open the terminal
11. Run `ssh <username>@<public-ip>`
12. Run `sudo apt-get update`
13. Run `sudo apt-get install openjdk-8-jdk`
14. Run `java -version`
15. Run `wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -`
16. Run `sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'`
17. Run `sudo apt-get update`
18. Run `sudo apt-get install jenkins`
19. Run `sudo systemctl start jenkins`
20. Run `sudo systemctl status jenkins`

#### Setting up New Agent in Jenkins

1. Open Jenkins
2. Click on `Manage Jenkins`
3. Click on `Manage Nodes and Clouds`
4. Click on `New Node`
5. Enter the node name as `azure-ubuntu-agent`
6. Select `Permanent Agent`
7. Click on `OK`
8. Enter the details:
   - Remote root directory: `/home/<username>`
   - Labels: `ubuntu`
   - Launch method: `Launch agent via SSH`
   - Host: `<public-ip>`
   - Credentials: `Add` -> `Jenkins`
   - Host Key Verification Strategy: `Non verifying Verification Strategy`
9. Click on `Save`
10. Click on `azure-ubuntu-agent`
11. Click on `Launch agent`
12. Click on `Build Executor Status` to view the agent status
