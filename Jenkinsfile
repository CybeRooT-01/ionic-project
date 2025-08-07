pipeline {
    agent any

    tools {
        nodejs 'Nodejs20'
    }

    environment {
        NODE_ENV = 'development'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/CybeRooT-01/ionic-project.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Lint') {
            steps {
                sh 'npm run lint'
            }
        }

        stage('Test') {
            steps {
                sh 'npm run test'
            }
        }
    }

    post {
        success {
            echo '✅ Build passed !'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}
