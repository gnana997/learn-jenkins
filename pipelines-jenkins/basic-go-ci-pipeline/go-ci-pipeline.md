### Notes for setting up CI pipeline for basic go app

## Setting up Jenkins

1. Open `Manage Jenkins` -> `Manage Plugins` -> `Available` -> `Search for Go` -> `Install`
2. Do a safe restart of Jenkins

## Setting up Go Plugin

1. Open `Manage Jenkins` -> `Global Tool Configuration` -> `Go` -> `Add Go` -> `Install automatically`
2. Click on `Save`

## Setting up a new Jenkins Job

1. Open Jenkins Dashboard
2. Click on `New Item`
3. Enter the item name as `go-ci-pipeline` and select `Pipeline`
4. Click on `OK`
5. In the Pipeline section, upload the script in Jenkinsfile in the folder
6. Click on `Save`
7. Click on `Build Now` to run the pipeline
8. Click on the build number to view the pipeline execution
