pipeline {
    agent any 
    stages {
        stage('Code Checkout') { 
            steps {
                git credentialsId: 'GithubID', url: 'https://github.com/itrainpulsars/maven-example.git'
            }
        }
        stage('Build') { 
            steps {
              withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6.1') {
               sh 'mvn clean compile'
             }
            }
        }
        stage('Test') { 
            steps {
               withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6.1') {
               sh 'mvn test'
             }  
            }
        }
        stage('Package') { 
            steps {
              withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6.1') {
               sh 'mvn package'
             }  
            }
        }
        stage('Docker Image') { 
            steps {
             sh 'echo docker image is build'   
            }
        }
        stage('Deploy to Dev') { 
            steps {
             sh 'echo Deploy to Dev'   
            }
        }
        stage('Deploy to prod') { 
            steps {
              sh 'echo Deploy to Prod'  
            }
        }
    }
}
