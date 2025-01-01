pipeline {
    agent any

    environment {
        ANSIBLE_INVENTORY = '/etc/ansible/hosts'
        ANSIBLE_PLAYBOOK = '/etc/ansible/capstone.yml'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/crispypotato/mthree.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: "${ANSIBLE_PLAYBOOK}",
                    inventory: "${ANSIBLE_INVENTORY}"
                )
            }
        }
    }
}
