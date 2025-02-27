pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout([
                        $class: 'GitSCM',
                        branches: [[name: '*/main']],
                        userRemoteConfigs: [[
                            url: 'git@github.com:Marji-Filkom/myapp-ci-cd.git',
                            credentialsId: 'github-ssh-key'
                        ]]
                    ])
                }
            }
        }
    }
}
