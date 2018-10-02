pipeline {
  agent none
  stages {
    stage('Ansible') {
      agent {
        docker {
          image 'varunchopra/ansible:windows'
          args '--user ansible'
        }

      }
      environment {
        RDP_USER = 'testuser191'
        REMOTE_PASS = 'myTempPassword123!'
        ANSIBLE_CONFIG = './ansible.cfg'
      }
      steps {
        ansiblePlaybook(playbook: 'main.yml', disableHostKeyChecking: true)
      }
    }
  }
}