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

                sh "mvn clean package"
            }
        }
        stage('Build Docker image'){
            steps {
                sh 'docker build -t arun1801docker/docker_jenkins_pipeline:${BUILD_NUMBER} .'
            }
        }
    }
}
