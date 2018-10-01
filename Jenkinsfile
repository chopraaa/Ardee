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
      steps {
        ansiblePlaybook(playbook: 'main.yml', become: true, disableHostKeyChecking: true)
      }
    }
  }
}