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
        sh '''touch testfile
ls -la
pwd'''
        ansiblePlaybook 'main.yml'
      }
    }
  }
}