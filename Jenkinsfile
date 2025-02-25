pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Marji-Filkom/my-project.git'
            }
        } 
        stage('Build') {
            steps {
                mvn 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                mvn 'mvn test'
            }
        }
    }
}
