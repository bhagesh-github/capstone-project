pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/<your-repo>.git'
            }
        }

        stage('Deploy to AWS') {
            steps {
                sh '''
                ansible-playbook -i inventory.ini playbook-aws.yaml
                '''
            }
        }

        stage('Deploy to Azure') {
            steps {
                sh '''
                ansible-playbook -i inventory.ini playbook-azure.yaml
                '''
            }
        }
    }
}
