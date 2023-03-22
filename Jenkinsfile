pipeline {
    agent any

    stages {
        stage('docker') {
            steps {
                sh '''
               sudo docker build -t apache:2 .
               sudo docker run -d -p 1000:80 apache:2 
               aws ecr get-login-password --region us-east-1 | sudo docker login --username AWS --password-stdin 101045478775.dkr.ecr.us-east-1.amazonaws.com
               sudo docker build -t 101045478775.dkr.ecr.us-east-1.amazonaws.com/new-ecr:2 .
               sudo docker push 101045478775.dkr.ecr.us-east-1.amazonaws.com/new-ecr:2 '''
            }
        }
    }
}