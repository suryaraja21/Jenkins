pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages {

        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout') {
            steps {
                checkout scm
                echo 'Source code checked out from Git'
                bat 'dir'
            }
        }

        stage('Build') {
            steps {
                bat 'javac Main.java'
            }
        }

        stage('Test') {
            steps {
                bat 'python hello.py'
                bat 'java Main'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESSFUL'
        }
        failure {
            echo 'BUILD FAILED'
        }
        always {
            echo 'Pipeline execution completed'
        }
    }
}
