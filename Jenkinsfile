pipeline {
  agent any
  stages {
    stage('get status') {
      steps {
        echo '"${WORKSPACE}"'
        dir(path: 'blockchain')
      }
    }
  }
}