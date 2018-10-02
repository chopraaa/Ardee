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
        pwd()
        git(url: 'https://github.com/chopraaa/automatic-octo-spork.git', credentialsId: 'chopraaa-git')
        ansiblePlaybook(playbook: 'main.yml', become: true, disableHostKeyChecking: true, inventory: '${WORKSPACE}/inventory')
      }
    }
  }
}