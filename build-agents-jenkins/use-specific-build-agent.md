### Notes to Use a specific build agent in Jenkins

#### Setting up Jenkins

1. Open `Manage Jenkins` -> `Manage Plugins` -> `Available` -> `Search for Go` -> `Install`
2. Do a safe restart of Jenkins

#### Setting up Go Plugin

1. Open `Manage Jenkins` -> `Global Tool Configuration` -> `Go` -> `Add Go` -> `Install automatically`
2. Click on `Save`

#### Setting up a new Jenkins Job

1. Open Jenkins Dashboard
2. Click on `New Item`
3. Enter the item name as `go-ci-pipeline` and select `Freestyle project`
4. Click on `OK`
5. In the General section, select `Restrict where this project can be run`
6. Enter the label expression as `docker` or the label of the specific build agent
7. If lable matches a specific build agent, It will show the build agent name right below the label expression
8. Add a basic shell script in the Build section to test the build agent
9. Click on `Save`
10. Click on `Build Now` to run the pipeline
11. Click on the build number to view the pipeline execution
