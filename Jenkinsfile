pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        git 'https://github.com/dev00/devops-content.git'
        ansiblePlaybook(playbook: 'webservers.yml', become: true, colorized: true, sudo: true)
      }
    }
  }
}