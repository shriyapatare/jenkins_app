pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/simple-web-app.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'  // Add a build script if necessary
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'  // Add test command
            }
        }
        stage('Deploy') {
            steps {
                sh 'npm start'
            }
        }
    }
}

