pipeline {
  agent any
  stages {
    stage('init') {
      steps {
        sh 'cd blockchain'
      }
    }
    stage('get status') {
      steps {
        timeout(time: 3, unit: 'MINUTES') {
          waitUntil() {
            script {
              return getBitmarkMode("localhost:2131")
            }

          }

        }

      }
    }
  }
}