pipeline {
  agent none
  stages {
    stage('Initialize') {
      steps {
        echo 'This is my first pipeline!'
      }
    }
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
      }
      steps {
        ansiblePlaybook(playbook: 'main.yml', become: true, disableHostKeyChecking: true, inventory: '${WORKSPACE}/inventory')
      }
    }
  }
}