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
mv testProjectJenkins-0.1.war testProjectJenkins.war'''
      }
    }

    stage('Unzip') {
      steps {
        sh '''cd /var/lib/jenkins/workspace/warFileCreation/target
7za x testProjectJenkins.war -otestProjectJenkins
'''
      }
    }

  }
}