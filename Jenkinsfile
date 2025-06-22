pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main',
            url: 'https://github.com/naveenps163/ansible-play.git',
            credentialsId: 'github-creds' // add your GitHub credentials
      }
    }

    stage('Run Cleanup Playbook') {
      steps {
        // Use Ansible plugin if installed
        ansiblePlaybook(
          inventory: 'hosts',
          playbook: 'cleanup_kali.yml',
          credentialsId: 'kali-ssh-key',
          colorized: true
        )
      }
    }
  }
}
