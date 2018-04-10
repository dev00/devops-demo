pipeline {
  agent any
  stages {
    stage('Deploy') {
      steps {
        git 'https://github.com/dev00/devops-content.git'
        ansiblePlaybook(playbook: 'webservers.yml', colorized: true, disableHostKeyChecking: true, inventory: 'hosts.ini', credentialsId: 'demo_access')
      }
    }
    stage('Test') {
      steps {
        sh 'find . -name tests.py -exec py.test -v {} --connection=ansible --hosts=\'web*\' --ansible-inventory=hosts.ini \\;'
      }
    }
  }
}