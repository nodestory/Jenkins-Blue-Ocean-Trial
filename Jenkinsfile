pipeline {
  agent any
  stages {
    stage('get status') {
      steps {
        echo '"${WORKSPACE}"'
        dir(path: 'blockchain')
        ws(dir: 'blockchain')
        sleep(unit: 'MINUTES', time: 1)
      }
    }
  }
  environment {
    test = 'test'
  }
}