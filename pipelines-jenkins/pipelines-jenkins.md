## Pipelines with Jenkins

### Jenkins Pipeline file Example

```
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
```

### Jenkins Pipeline Syntax

- pipeline: This block contains the entire pipeline script.
- agent: This block specifies the execution point for the entire pipeline.
- stages: This block contains a sequence of one or more stages that the Jenkins pipeline will execute.
- stage: This block contains a sequence of one or more steps that the Jenkins pipeline will execute.
- steps: This block contains a sequence of one or more commands that the Jenkins pipeline will execute.

### Run a Sample Jenkins Pipeline

1. Open Jenkins and click on `New Item`.
2. Enter the item name as `pipeline-demo` and select `Pipeline`.
3. Click on `OK`.
4. In the Pipeline section, select `Pipeline script` and enter the following script:
   ```groovy
   pipeline {
       agent any
       stages {
           stage('Build') {
               steps {
                   echo 'Building..'
               }
           }
           stage('Test') {
               steps {
                   echo 'Testing..'
               }
           }
           stage('Deploy') {
               steps {
                   echo 'Deploying....'
               }
           }
       }
   }
   ```
5. Click on `Save`.
6. Click on `Build Now` to run the pipeline.
7. Click on the build number to view the pipeline execution.
8. Click on the `Console Output` to view the pipeline execution logs.
9. The pipeline will execute the `Build`, `Test`, and `Deploy` stages sequentially.

### Jenkins Pipeline triggers available

- Poll SCM: This trigger polls the SCM at a specified interval and builds the project if changes are detected.
- Build after other projects are built: This trigger builds the project after other projects are built.
- Build periodically: This trigger builds the project periodically.
- GitHub hook trigger for GITScm polling: This trigger builds the project when a push is made to the GitHub repository.
- Build when a change is pushed to GitHub: This trigger builds the project when a change is pushed to the GitHub repository.
- Trigger builds remotely: This trigger builds the project remotely.
