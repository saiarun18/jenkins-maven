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

                sh "mvn package"
            }
        }
        stage('Build Docker image'){
            steps {
                sh 'docker build -t arun1801docker/docker_jenkins_pipeline:${BUILD_NUMBER} .'
            }
        }
        stage('Docker Login'){
            steps {
                 withCredentials([string(credentialsId: 'DockerId5', variable: 'Dockerpwd')]) {
                          sh "docker login -u arun1801docker -p ${Dockerpwd}"
                 }
            }
        }           
        stage('Docker Push'){
            steps {
                sh 'docker push arun1801docker/docker_jenkins_pipeline:${BUILD_NUMBER}'
            }
        }
    }
}
