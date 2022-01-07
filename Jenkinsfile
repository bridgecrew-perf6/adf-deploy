pipeline {
    agent any

    stages {
        stage('Check Out SCM') {
            steps {
                scripts{
                    checkout scm
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