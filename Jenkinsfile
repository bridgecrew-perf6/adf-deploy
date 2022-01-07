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
                    ps 'az login'
                    ps 'az account set --subscription KarthikMLSubscription'
                    ps 'az config set extension.use_dynamic_install=yes_without_prompt'
                    ps 'az extension add --name datafactory'
                    ps 'az datafactory list'
                    ps 'Set-AzDataFactoryV2LinkedService -ResourceGroupName "Datafactory-QA" -DataFactoryName "adf-karthik-qa" -Name "adls1_test" -File "C:\\Users\\karthikroopa\\Downloads\\Copy_pl_support_live\\linkedService\\adls2.json" | Format-List'
                }
            }
        }
    }
}