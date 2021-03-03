pipeline {
  agent any
  stages {
    stage('Pull The Project') {
      parallel {
        stage('Pull The Project') {
          steps {
            build 'Git Pull Only'
          }
        }

        stage('1') {
          steps {
            echo 'this is one'
          }
        }

        stage('slp') {
          steps {
            sleep(unit: 'MINUTES', time: 2)
          }
        }

        stage('2') {
          steps {
            echo 'quak'
          }
        }

        stage('3') {
          steps {
            retry(count: 5) {
              sh 'echo "echo"'
            }

          }
        }

        stage('4') {
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

  }
}