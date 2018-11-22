pipeline {
  agent any
  stages {
    stage('get status') {
      steps {
        git(url: 'git@github.com:bitmark-inc/automation.git', branch: 'master')
      }
    }
  }
}