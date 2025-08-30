jenkins: pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'git@github.com:olaniyikolawole744/jen-ans-pro-gra.git'
            }
        }
        stage('Build & Test') {
            steps {
                sh 'echo "Run unit tests here"'
            }
        }
        stage('Deploy with Ansible') {
            steps {
                sh 'ansible-playbook playbook.yml -i inventory.yml --vault-password-file /var/lib/jenkins/.ssh/.vault_pass.txt -vvvvv '
            }
        }
        stage('Install Grafana and Prometheus') {
            steps {
                sh 'ansible-playbook playbook-2.yml -i inventory.yml --vault-password-file /var/lib/jenkins/.vault_pass.txt -vvvvv '
            }
        }
    }
}
