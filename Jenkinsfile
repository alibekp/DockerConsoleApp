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
         stage("Release Stage") {
            steps {
                bat 'dotnet build %WORKSPACE%\\DockerConsoleApp.sln /p:PublishProfile=" %WORKSPACE%\\DockerConsoleApp\\Properties\\PublishProfiles\\FolderProfile.pubxml" /p:Platform="Any CPU" /p:DeployOnBuild=true /m'
            }
        }
        stage ("Docker build") {
          steps {
            script {
                    bat 'bat docker build -t dockeralibek/library -f Dockerfile .'
                    bat 'docker push'
                }
            }
        }
    }
}
