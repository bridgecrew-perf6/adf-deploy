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
                    subscriptiondev = 'KarthikMLSubscription'
                    bat 'az login'
                    bat 'az account set --subscription KarthikMLSubscription'
                    bat 'az config set extension.use_dynamic_install=yes_without_prompt'
                    bat 'az extension add --name datafactory'
                    bat 'az datafactory list'
                }
            }
        }
    }
}