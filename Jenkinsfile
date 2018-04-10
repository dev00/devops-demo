pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        git(url: 'git@github.com:dev00/devops-content.git', branch: 'master')
        ansiblePlaybook(playbook: 'webservers.yml', colorized: true, disableHostKeyChecking: true, inventory: 'hosts.ini', sudo: true)
      }
    }
  }
}