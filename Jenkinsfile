pipeline {
    agent any
	environment {     
         DOCKERHUB_CREDENTIALS= credentials('dockeralibek-dockerhub')     
    } 
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
                    bat 'docker build -t dockerimage:latest .'
            }
        }
	    stage ("Docker create") {
          steps {
                    bat 'docker create --name dockercontainer dockerimage'
            }
        }
        /*stage('Login to Docker Hub') {      	
            steps {                       	
                	bat 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'                		
	                echo 'Login Completed'      
                  }           
         }
         stage ("Docker push") {
          steps {
                    bat 'docker push dockeralibek/library:latest'
            }
        }*/
    }
}
