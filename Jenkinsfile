pipeline {
    agent any
    stages {
        stage ("Docker build") {
          steps {
		    bat 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\TestPipeline2\\'  
                    bat 'docker build -t dockeralibek/library:latest .'
            }
        }
        }
    }
