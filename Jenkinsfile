pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
                git 'https://github.com/karthik-1990/adf-deploy'
            }
        }
        stage('Deploy code to QA env') {
            steps {
                script{
                    sh """#!/bin/bash
                    echo "Loggin into Azure Account"
                    """
                }
            }
        }
    }
}