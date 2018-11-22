pipeline {
  agent any
  stages {
    stage('get status') {
      steps {
        git(url: 'https://github.com/bitmark-inc/automation', branch: 'master')
      }
    }
  }
}