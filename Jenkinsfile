pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        git 'https://github.com/dev00/devops-content.git'
        ansiblePlaybook(playbook: 'webservers.yml', colorized: true, disableHostKeyChecking: true, inventory: 'hosts.ini', credentialsId: 'demo_access')
      }
    }
  }
}