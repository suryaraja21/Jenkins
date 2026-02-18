pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
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
    post{
        success {
            echo 'BUILD SUCCESSFULL'
        }
        failute {
            echo 'BUILD FAILED'
        }always {
            echo 'PIPELINE EXECUTION COMPLETED'
        }
    }
}
