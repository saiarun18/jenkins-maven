pipeline {
    agent any 
    stages {
        stage('SCM Download') { 
            steps {
               git 'https://github.com/saiarun18/jenkins-maven.git'
            }
        }
        stage('Compile and Clean') { 
            steps {

                sh "mvn clean install"
            }
        }
    }
}
