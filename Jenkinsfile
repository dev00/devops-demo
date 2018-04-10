pipeline {
  agent any
  stages {
    stage('') {
      steps {
        git(url: 'git@github.com:dev00/devops-demo.git', branch: 'master')
        ansiblePlaybook(playbook: 'webservers.yml', colorized: true, disableHostKeyChecking: true, inventory: 'hosts.ini', sudo: true)
      }
    }
  }
}