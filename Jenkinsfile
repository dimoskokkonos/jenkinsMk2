pipeline {
  agent any
  stages {
    stage('Pull The Project') {
      parallel {
        stage('1') {
          steps {
            build 'Git Pull Only'
          }
        }

        stage('2') {
          steps {
            echo 'this is one'
          }
        }

        stage('3') {
          steps {
            sleep(unit: 'SECONDS', time: 66)
          }
        }

        stage('4') {
          steps {
            echo 'quak'
          }
        }

        stage('5') {
          steps {
            retry(count: 5) {
              sh 'echo "echo"'
            }

          }
        }

        stage('6') {
          steps {
            sh 'cd /home/dkokkonos'
          }
        }

      }
    }

    stage('STEP 2') {
      steps {
        echo 'THIS IS STEP 2'
      }
    }

    stage('STEP 3') {
      parallel {
        stage('1') {
          steps {
            echo '3333'
          }
        }

        stage('2') {
          steps {
            timeout(time: 1)
          }
        }

        stage('3') {
          steps {
            echo 'HELLO'
          }
        }

        stage('4') {
          steps {
            build 'warFileCreation'
          }
        }

        stage('5') {
          steps {
            sleep 15
          }
        }

      }
    }

    stage('STEP 4') {
      steps {
        echo 'STEP 4'
      }
    }

  }
}