pipeline {
  agent any
  stages {
    stage('init') {
      steps {
        sh '''def getBitmarkdMode(name) {
    def mode = sh \'curl -k https://${name}/bitmarkd/details | jq -r .mode\'
    return mode ==~ "Normal"
}

cd blockchain'''
        }
      }
      stage('get status') {
        steps {
          timeout(time: 3, unit: 'MINUTES') {
            waitUntil() {
              script {
                return getBitmarkMode("localhost:2131");
              }

            }

          }

        }
      }
    }
  }