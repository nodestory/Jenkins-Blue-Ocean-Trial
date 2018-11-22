pipeline {
  agent any
  stages {
    stage('get status') {
      steps {
        timeout(time: 3, unit: 'MINUTES') {
          waitUntil() {
            script {
              def mode = sh 'curl -k https://localhost:2131/bitmarkd/details | jq -r .mode'
              return mode ==~ "Normal"
            }

          }

        }

      }
    }
  }
}