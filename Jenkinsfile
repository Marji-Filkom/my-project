pipeline {
    agent any  // Menjalankan pipeline di agent mana saja

    environment {
        MVN_HOME = "D:\\2025 Master\\apache-maven-3.9.9-bin\\apache-maven-3.9.9"
        JAVA_HOME = "C:\\Program Files\\Java\\jdk-21"
        PATH = "${MVN_HOME}\\bin;${JAVA_HOME}\\bin;${PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/user/repo.git'  // Ganti dengan repo Git kamu
                echo "Tahap Checkout..."
            }
        }

        stage('Build') {
            steps {
                script {
                    //sh 'mvn clean package'  // Build project dengan Maven
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    //sh 'mvn test'  // Menjalankan unit test
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying application..."
                    // Tambahkan perintah deploy sesuai kebutuhan, misalnya:
                    // sh 'scp target/*.jar user@server:/path/to/deploy/'
                }
            }
        }
    }

    post {
        success {
            echo "Pipeline berhasil!"
        }
        failure {
            echo "Pipeline gagal!"
        }
    }
}
