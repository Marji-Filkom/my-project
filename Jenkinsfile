pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Marji-Filkom/my-project.git', branch: 'main'
            }
        }
        
        stage('Build') {
            steps {
                echo "Building the application..."
                // Tambahkan perintah build, misalnya:
                // sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                // Tambahkan perintah testing, misalnya:
                // sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application..."
                sh 'cp target/*.jar "D:\deploy-folder"' 
            }
        }
    }
}
