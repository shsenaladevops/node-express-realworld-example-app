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
                git branch: 'main',
                    url: 'https://github.com/gothinkster/node-express-realworld-example-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'npm test'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }
    }

    post {
        success {
            echo 'NodeJS CI SUCCESS'
        }
        failure {
            echo 'NodeJS CI FAILED'
        }
    }
}
