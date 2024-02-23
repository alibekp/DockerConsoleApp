pipeline {
    agent any
    stages {
        stage('Build') {
           steps {
               build -t sample-alibek-image -f Dockerfile .
            }
        }
    }
}
