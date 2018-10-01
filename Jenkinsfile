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
        sh '''ls -la /

'''
        ansiblePlaybook 'main.yml'
      }
    }
  }
}