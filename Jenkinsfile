pipeline {
  agent any
  stages {
    stage('Pull The Project') {
      steps {
        build 'Git Pull Only'
      }
    }

    stage('Run PipeLine') {
      steps {
        build 'jenkinsMk2'
      }
    }

  }
}