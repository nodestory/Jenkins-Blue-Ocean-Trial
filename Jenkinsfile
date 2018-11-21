pipeline {
  agent any
  stages {
    stage('node-[adt]1') {
      parallel {
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
        stage('node-d1') {
          steps {
            echo 'd1'
          }
        }
        stage('node-t1') {
          steps {
            echo 't1'
          }
        }
      }
    }
    stage('wait for 1st batch') {
      steps {
        echo 'waiting'
      }
    }
    stage('node-[adt]2') {
      parallel {
        stage('node-a2') {
          steps {
            echo 'a2'
          }
        }
        stage('node-d2') {
          steps {
            echo 'd2'
          }
        }
        stage('node-t2') {
          steps {
            echo 't2'
          }
        }
      }
    }
    stage('wait for 2nd batch') {
      steps {
        echo 'wait'
      }
    }
  }
}