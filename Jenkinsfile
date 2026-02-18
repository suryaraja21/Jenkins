pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    triggers {
        pollSCM('* * * * *')
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
                bat 'dir'
            }
        }

        stage('Build') {
            steps {
                bat 'javac WrongFileName.java'
            }
        }

        stage('Test') {
            steps {
                bat 'python hello.py'
                bat 'java Main'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '*.class', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'CI PIPELINE SUCCESSFUL'
        }
        failure {
            echo 'CI PIPELINE FAILED'
        }
        always {
            echo 'CI execution completed'
        }
    }
}
