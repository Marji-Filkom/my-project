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
                   git config --global user.email "xmarjiy@gmail.com"
                   git config --global user.name "Marji-Filkom"

                   git add -f target/*
                   git commit -m "Deploy update from Jenkins"

                   # Pastikan tidak ada konflik sebelum push
                   git pull origin ${BRANCH} --rebase || git pull origin ${BRANCH} --allow-unrelated-histories

                   git push origin ${BRANCH}
                 }
            }
        }
    }
}
