pipeline {
    agent any
    stages {
        stage ("Docker build") {
          steps {
		    bat 'cd C:\\Users\\alibek.prmanov\\Desktop\\DockerConsoleApp\\DockerConsoleApp-master'
                    bat 'docker build -t dockeralibek/library:latest .'
            }
        }
    }
}
