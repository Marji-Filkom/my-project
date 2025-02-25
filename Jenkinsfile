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
                sh 'mvn clean package'  // Sesuaikan dengan kebutuhan
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }
}
