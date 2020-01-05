## Jenkins Notes




### General
- Add project parameters under **This project is parameterised**
### Source Code Management
- Avoid pulling full github repo to run job, pull only code you need
    - Under SCM, addtional behaviours -> **Sparse Checkout Paths**

### Build Triggers
- Usually use Github hook trigger (configure webhook in Github to hit Jenkins endpoint notifying Jenkins to build)

### Jenkinsfile
- script containing definition and steps to execute in a Jenkins Pipeline
- Written using a DSL based on Groovy
- Eg:
    ```groovy
    #!/usr/bin/groovy
    // Scripted Pipeline
    node {
        stage('Build') {
            echo 'Building'
        }
    }

    //Declarative Pipeline
    pipeline {
        agent any
        stages {
            stage('Build') {
                steps {
                    echo 'Building'
                }
            }
        }
    }
    ```

### BlueOcean
- New user interface of Jenkins 2.0 (UI for pipelines)
- Build pipes interactively, requires Github personal token
- Automatically detects Jenkinsfile to visualize pipelines
