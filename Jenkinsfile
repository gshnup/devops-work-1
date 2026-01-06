pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git '<your-repo-url>'
            }
        }

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
                docker run -d -p 8081:80 --name myweb mywebapp
                '''
            }
        }
    }
}
