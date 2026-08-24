pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running JavaScript application...'
                sh 'node src/main/javascript/hello.js'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'mkdir -p deploy'
                sh 'cp src/main/javascript/hello.js deploy/'
            }
        }
    }

    post {

        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'CI/CD Pipeline failed!'
        }
    }
}
