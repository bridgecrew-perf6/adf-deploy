pipeline {
    agent any

    stages {
        stage('Check Out SCM') {
            steps {
                scripts{
                    git credentialsId: 'karthik-1990', url: 'https://github.com/karthik-1990/adf-deploy.git'
                }
                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}