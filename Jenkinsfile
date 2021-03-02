pipeline {
  agent any
  stages {
    stage('Creating WAR file') {
      steps {
        build 'warFileCreation'
      }
    }

    stage('Edit War File Name') {
      steps {
        sh '''cd /var/lib/jenkins/workspace/warFileCreation/target
echo pwd'''
      }
    }

  }
}