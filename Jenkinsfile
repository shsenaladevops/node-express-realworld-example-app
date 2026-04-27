pipeline {
    agent any

    tools {
        nodejs 'node-18'
    }

    triggers {
        githubPush()
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/gothinkster/node-express-realworld-example-app.git'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Unit Tests (Real-Time)') {
            steps {
                sh 'npm test'
            }
        }

        stage('Lint') {
            steps {
                sh 'npm run lint || true'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build || true'
            }
        }
    }
}
