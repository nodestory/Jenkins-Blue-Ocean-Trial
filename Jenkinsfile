pipeline {
  agent any
  stages {
    stage('node-a1') {
      steps {
        timeout(unit: 'MINUTES', time: 10) {
          echo 'do something'
          sleep 10
          waitUntil() {
            script {
              def r = sh returnStatus: true, script: '''
(echo '{"id":"1","method":"Node.Info","params":[{}]}'; sleep 1; echo Q) | openssl s_client -connect node-a1.test.bitmark.com:2130 -quiet
'''
              return (r == 0)
            }

          }

        }

      }
    }
  }
}