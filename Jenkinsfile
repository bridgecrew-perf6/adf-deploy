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
                    powershell 'az login'
                    powershell 'az account set --subscription KarthikMLSubscription'
                    powershell 'az config set extension.use_dynamic_install=yes_without_prompt'
                    powershell 'az extension add --name datafactory'
                    powershell 'az datafactory list'
                    powershell 'Set-AzDataFactoryV2LinkedService -ResourceGroupName "Datafactory-QA" -DataFactoryName "adf-karthik-qa" -Name "adls1_test_1" -File "C:\\Users\\karthikroopa\\Downloads\\Copy_pl_support_live\\linkedService\\adls1.json" | Format-List'
                    powershell 'Set-AzDataFactoryV2LinkedService -ResourceGroupName "Datafactory-QA" -DataFactoryName "adf-karthik-qa" -Name "adls1_test_2" -File "C:\\Users\\karthikroopa\\Downloads\\Copy_pl_support_live\\linkedService\\adls2.json" | Format-List'
                }
            }
        }
    }
}