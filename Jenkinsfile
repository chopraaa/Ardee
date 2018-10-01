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
        dockerfile {
          filename 'ansible-Dockerfile'
        }

      }
      steps {
        sh 'mkdir /.ansible'
        ansiblePlaybook(playbook: 'main.yml', become: true, disableHostKeyChecking: true)
      }
    }
  }
}