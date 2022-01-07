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
                    //powershell 'Set-AzDataFactoryV2LinkedService -ResourceGroupName "Datafactory-QA" -DataFactoryName "adf-karthik-qa" -Name "adls1" -File "C:\\Users\\karthikroopa\\Downloads\\Copy_pl_support_live\\linkedService\\adls1.json" | Format-List'
                    //powershell 'Set-AzDataFactoryV2LinkedService -ResourceGroupName "Datafactory-QA" -DataFactoryName "adf-karthik-qa" -Name "adls2" -File "C:\\Users\\karthikroopa\\Downloads\\Copy_pl_support_live\\linkedService\\adls2.json" | Format-List'
                    //powershell 'Set-AzDataFactoryV2Dataset -DataFactoryName "adf-karthik-qa" -ResourceGroupName "Datafactory-QA" -Name "csv1" -DefinitionFile "C:\\Users\\karthikroopa\\Downloads\\Copy_pl_support_live\\dataset\\csv1.json" | Format-List'
                    //powershell 'Set-AzDataFactoryV2Dataset -DataFactoryName "adf-karthik-qa" -ResourceGroupName "Datafactory-QA" -Name "csv2" -DefinitionFile "C:\\Users\\karthikroopa\\Downloads\\Copy_pl_support_live\\dataset\\csv2.json" | Format-List'
                    powershell 'Set-AzDataFactoryV2Pipeline -DataFactoryName "adf-karthik-qa" -ResourceGroupName "Datafactory-QA" -Name "Copy_pl" -DefinitionFile "C:\\Users\\karthikroopa\\.jenkins\\workspace\\ADF_JSON_Template\\pipeline\\Copy_pl.json" | Format-List'
                }
            }
        }
    }
}