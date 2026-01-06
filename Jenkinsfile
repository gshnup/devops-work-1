pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop myweb || true
                docker rm myweb || true
                docker run -d -p 8082:80 --name myweb mywebapp
                '''
            }
        }
    }
}
