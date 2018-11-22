pipeline {
  agent any
  stages {
    stage('get status') {
      steps {
        git(url: 'git@github.com:bitmark-inc/automation.git', branch: 'master', credentialsId: '96df0462-4b21-4432-ab9e-6590e19bfea2')
      }
    }
  }
}