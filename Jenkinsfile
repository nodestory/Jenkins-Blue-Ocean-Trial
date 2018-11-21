pipeline {
  agent any
  stages {
    stage('node-a1') {
      steps {
        timeout(unit: 'MINUTES', time: 10) {
          echo 'do something'
          sleep 10
          waitUntil() {
            sh '''node_status=$((echo \'{"id":"1","method":"Node.Info","params":[{}]}\'; sleep 1; echo Q) | openssl s_client -connect node-a1.test.bitmark.com:2130 -quiet | jq .result.mode);
return (node_status == \'"Normal"\');'''
          }

        }

      }
    }
  }
}