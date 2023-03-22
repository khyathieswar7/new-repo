pipeline {
    agent any

    stages {
        stage('docker') {
            steps {
                sh '''
               sudo docker build -t apache:1 .
               sudo docker run -d -p 1000:80 apache:1 '''
            }
        }
    }
}