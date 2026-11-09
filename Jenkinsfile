@Library('Shared') _
pipeline {
    agent any

    triggers {
        githubPush()
    }

 

    stages {

               stage('Test Shared Library') {
            steps {
                hello()
            }
        }
        stage('Code') {
            steps {
                echo 'Checking out code'
                checkout scm
                echo 'Checkout completed'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Docker image'
                sh 'docker build -t notes-app:latest .'
            }
        }
    }
}
