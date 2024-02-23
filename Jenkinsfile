pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
        checkout scm
            }
      }
 stage('Build Stage') {
            steps {
                bat 'C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\TestPipeline2\\DockerConsoleApp.sln --configuration Release'
            }
        }
        stage('Build on Docker') {
           steps {
               sh 'docker build -t sample-alibek-image -f Dockerfile .'
            }
        }
    }
}
