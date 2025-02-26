pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                bat 'echo "Checkout..."'
            }
        }

        stage('Build') {
            steps {
                bat  'echo "Building the project..."'
                bat  'mvn clean package' // Contoh jika proyek menggunakan Maven
            }
        }

        stage('Test') {
            steps {
                bat  'echo "Running tests..."'
                bat  'mvn test' // Jalankan unit test jika pakai Maven
            }
        }

        stage('Deploy') {
            steps {
                bat  'echo "Deploying application..."'
                bat  'scp target/*.jar user@server:/deploy-path/' // Contoh deploy ke server
            }
        }
    }
}
