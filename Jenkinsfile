pipeline {
    agent any
    stages {
        stage('Clone repository') {
        checkout scm
      }
        stage('Build') {
           steps {
               sh 'docker build -t sample-alibek-image -f Dockerfile .'
            }
        }
    }
}
