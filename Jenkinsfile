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
        }

      }
      steps {
        ansiblePlaybook(playbook: 'main.yml', become: true, disableHostKeyChecking: true)
      }
    }
  }
}