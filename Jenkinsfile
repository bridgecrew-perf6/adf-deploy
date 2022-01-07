pipeline {
    agent any

    stages {
        stage('Check Out SCM') {
            steps {
                checkout SCM
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