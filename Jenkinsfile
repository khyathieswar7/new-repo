pipeline {
    agent any

    stages {
        stage('docker') {
            steps {
                sh '''
                docker build -t apache:1 .
                docker run -d -p 1000:80 apache:1 '''
            }
        }
    }
}