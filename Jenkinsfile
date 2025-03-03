pipeline {
    agent any

    environment {
        BRANCH = 'main'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/Marji-Filkom/my-project.git', branch: 'main'

            }
        }

        stage('Build Project') {
            steps {
                bat 'mvn clean package'  // Sesuaikan dengan proses build Anda
            }
        }

        stage('Deploy Output to GitHub') {
            steps {
                script {
                    bat """
                    git add .
                    git commit -m "Deploy update from Jenkins"
                    git push origin ${BRANCH}
                    """
                }
            }
        }
    }
}
