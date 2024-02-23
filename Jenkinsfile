pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
        checkout scm
            }
      }
stage('Build') {
 steps {
  bat "msbuild.exe ${workspace}
 }
}
        stage('Build') {
           steps {
               sh 'docker build -t sample-alibek-image -f Dockerfile .'
            }
        }
    }
}
