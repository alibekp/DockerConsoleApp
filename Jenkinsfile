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
 bat "msbuild.exe ${DockerConsoleApp}\\DockerConsoleApp\\DockerConsoleApp.sln /nologo /nr:false  
                              /p:platform=\"x64\" /p:configuration=\"release\" 
                              /p:PackageCertificateKeyFile=<path-to-certificate-file>.pfx /t:clean;restore;rebuild"
 }
}
        stage('Build') {
           steps {
               sh 'docker build -t sample-alibek-image -f Dockerfile .'
            }
        }
    }
}
