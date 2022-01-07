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
                    bat 'cd C:\Users\karthikroopa\Downloads\Copy_pl_support_live\pipeline'
                    bat 'az datafactory pipeline create --resource-group Datafactory-QA --factory-name adf-karthik-qa --name ADF_Test --pipeline @Copy_pl.json'
                }
            }
        }
    }
}