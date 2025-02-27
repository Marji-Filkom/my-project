// Jenkinsfile
pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', credentialsId: 'github-ssh-key', url: 'git@github.com:Marji-Filkom/myapp-ci-cd.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                bat 'copy target\*.jar C:\deploy-folder'
            }
        }
    }
}
