pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t angular-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f angular-container || true
                docker run -d -p 8082:80 --name angular-container angular-app
                '''
            }
        }
    }
}
