pipeline {
    agent any

    environment {
        PYTHON_VERSION = "3.10"  // Ganti sesuai kebutuhan
        VENV_DIR = "venv"        // Nama virtual environment
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/user/repo.git'  // Ganti dengan repo Python-mu
            }
        }

        stage('Setup Python') {
            steps {
                script {
                    def pythonHome = tool name: "Python ${PYTHON_VERSION}", type: "hudson.plugins.python.PythonInstallation"
                    env.PATH = "${pythonHome}/bin:${env.PATH}"
                }
                sh 'python --version'
            }
        }

        stage('Create Virtual Env & Install Dependencies') {
            steps {
                sh '''
                python -m venv ${VENV_DIR}
                source ${VENV_DIR}/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                source ${VENV_DIR}/bin/activate
                pytest --junitxml=report.xml
                '''
            }
        }

        stage('Archive Test Results') {
            steps {
                junit 'report.xml'
            }
        }

        stage('Build Package') {
            steps {
                sh '''
                source ${VENV_DIR}/bin/activate
                python setup.py sdist
                '''
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'dist/*.tar.gz', fingerprint: true
            }
        }
    }

    post {
        always {
            sh 'rm -rf ${VENV_DIR}'
        }
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Check logs for errors.'
        }
    }
}
