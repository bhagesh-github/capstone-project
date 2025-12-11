pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/bhagesh-github/capstone-project.git'
            }
        }

        stage('Deploy to AWS') {
            steps {
                sh '''
                ansible-playbook -i inventory playbook-aws.yaml
                '''
            }
        }

        stage('Deploy to Azure') {
            steps {
                sh '''
                ansible-playbook -i inventory playbook-azure.yaml
                '''
            }
        }
    }
}
