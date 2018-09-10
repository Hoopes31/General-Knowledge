# Jenkins declarative pipelines

CI/CD as code

``` Jenkinsfile
pipeline {
    agent any              <-------- Execute the pipeline or any of its statges on any agent
    stages {               <-------- Stages object, defines all stages and there steps
        stage('Build') {   <-------- Stage object is named and holds a list of instruction _steps_
            steps {        <-------- Step object defines what actions should be taken in the stage
                //
            }
        }
        stage('Test') {
            steps {
                //
            }
        }
        stage('Deploy') {
            steps {
                //
            }
        }
    }
}
```

## Typical pipeline breakdown

1. Build Stage: where code is assembled, compiled, or packaged.
2. Test Stage: where tests are run against code and reports returned.
3. Deploy Stage: pushes built code to your deployment location

## Setting up a SCM based pipeline

1. Log into Jenkins and select **New Item**
2. Enter a pipeline name in the input field at the top of the page
3. Select **Pipeline**
4. Click "Ok"
5. Under the Pipeline header is a **Definition** field, select **Pipeline script from SCM**.
6. Under the **SCM** field, select your SCM.
7. Fill out your relative information, e.g. Repository URL, credentials for privates, Branches to build.
8. Under the **Script Path** field, type the name/path to your **Jenkinsfile**. Jenkins defaults the check to your root.

_Jenkinsfile script builder localhost:8080/pipeline-syntax/_

## Building a Jenkinsfile

### Tips and tricks

- `sh`: a shell script that will run your code in the given stages shell
- `bat`: a windows batch script that will run your code in the given stages shell
- `powershell`: a powershell script that will run your code in the given stages shell

### Environment variables

Setting environment variables can be achieved by adding an environment object to a stage object or the full pipeline e.g.,

```Dockerfile
pipeline {
  agent any
  environment {
    DEBUG_FLAGS = "Ah, Debug" <-------- Sets DEBUG_FLAGS for the entire pipeline
  }
  stage('Test') {
    environment {
      BUILD_ID = '1234' <-------- Sets BUILD_ID to 1234 for the 'Test' stage
    }
    steps {
      //
    }
}
```

Environment variables can be utilized by Jenkinsfiles through string interpolation. e.g.,

`echo "Running ${env.BUILD_ID}"`

_List of env variables can be found at http://localhost:8080/pipeline-syntax/globals#env on your Jenkins instance_
