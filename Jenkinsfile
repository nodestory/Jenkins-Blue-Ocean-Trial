pipeline {
  agent any
  stages {
    stage('node-a1') {
      steps {
        timeout(unit: 'MINUTES', time: 10) {
          echo 'do something'
          sleep 10
          waitUntil() {
            sh 'curl -I https://www.google.com.tw'
          }

        }

      }
    }
  }
}