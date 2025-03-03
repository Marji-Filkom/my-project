pipeline {
    agent any

    environment {
        GIT_CREDENTIALS = 'github-token'  
        REPO_URL = 'https://github.com/Marji-Filkom/my-project.git'
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
                    git add -f target/*  # Tambahkan file di folder target/
                    git commit -m "Deploy update from Jenkins"
                    git pull origin ${BRANCH} --rebase  # Hindari konflik
                    git push origin ${BRANCH}
                 }
            }
        }
    }
}
