pipeline {
    agent any
	environment {     
         DOCKERHUB_CREDENTIALS= credentials('dockeralibek-dockerhub')     
    } 
    stages {
        stage ("Docker build") {
          steps {
		    bat 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\TestPipeline2\\'  
                    bat 'docker build -t dockeralibek/library:latest .'
            }
        }
        stage('Login to Docker Hub') {      	
            steps {                       	
                	sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'                		
	                echo 'Login Completed'      
                  }           
         }
         stage ("Docker push") {
          steps {
                    bat 'docker push dockeralibek/library:latest'
            }
        }
    }
}
