pipeline {
    agent any
    stages {
        stage('Build') {
           steps {
               app = docker.build("getintodevops/hellonode")
            }
        }
    }
}
