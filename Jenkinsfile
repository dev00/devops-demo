pipeline {
  agent any
  stages {
    stage('Deploy Middleware') {
      steps {
        git 'https://github.com/dev00/devops-content.git'
        ansiblePlaybook(playbook: 'webservers.yml', colorized: true, disableHostKeyChecking: true, inventory: 'hosts.ini', credentialsId: 'demo_access')
      }
    }
    stage('Test Middleware') {
      steps {
        sh 'find . -name \'*_test.py\' -exec py.test -v {} --connection=ansible --hosts=\'web*\' --ansible-inventory=hosts.ini --junit-xml={}.xml \\;'
        sh 'ls -al'
      }
    }
  }
}