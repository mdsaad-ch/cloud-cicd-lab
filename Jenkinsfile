
pipeline {
    agent any

    environment {
        AWS_REGION = 'ap-south-1'
        AWS_ACCOUNT_ID = '486036174197'
        ECR_REPOSITORY = 'student-service'
        IMAGE_TAG = 'latest'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build and Test') {
            steps {
                sh 'python3 --version'
                sh 'python3 -m py_compile app.py'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t student-service:latest .'
            }
        }

        stage('ECR Login') {
            steps {
                sh 'aws ecr get-login-password --region $AWS_REGION | docker login --username AWS --password-stdin $AWS_ACCOUNT_ID.dkr.ecr.$AWS_REGION.amazonaws.com'
            }
        }

        stage('Docker Tag') {
            steps {
                sh 'docker tag student-service:latest $AWS_ACCOUNT_ID.dkr.ecr.$AWS_REGION.amazonaws.com/$ECR_REPOSITORY:$IMAGE_TAG'
            }
        }

        stage('Push to ECR') {
            steps {
                sh 'docker push $AWS_ACCOUNT_ID.dkr.ecr.$AWS_REGION.amazonaws.com/$ECR_REPOSITORY:$IMAGE_TAG'
            }
        }
    }
}
