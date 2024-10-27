pipeline {
    agent any
    tools {
        nodejs 'NodeJS' // Name of your NodeJS installation in Jenkins
        maven 'Maven'
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git url: 'https://github.com/shriyapatare/jenkins_app.git',
                branch: 'master'
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }
        stage('Build with Maven') {
            steps {
                // Build the application using Maven
                sh 'mvn clean package'
            }
        }
        stage('Run Tests') {
            steps {
                // Run npm test directly
                sh 'npm test'
            }
        }
        stage('Run Selenium Tests') {
            steps {
                // Run Selenium tests (this assumes you have a script for running your tests)
                // You may need to adjust this command based on your test setup
                sh 'mvn test -Dtest=BasicPageLoadTest'
            }
        }
    }
    post {
        success {
            echo 'Build and tests were successful!'
        }
        failure {
            echo 'Build or tests failed!'
        }
        always {
            // Clean up or send notifications
            echo 'Cleaning up...'
        }
    }
}

