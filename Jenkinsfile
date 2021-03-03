pipeline {
  agent any
  stages {
    stage('Creating WAR file') {
      steps {
        sh '''cd /var/lib/jenkins/workspace/warFileCreation/target
rm -f testProjectJenkins.war
rm -f testProjectJenkins.7z
rm -rf testProjectJenkins'''
        build 'warFileCreation'
      }
    }

    stage('Edit Name') {
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

    stage('Delete Libs') {
      steps {
        sh '''cd /var/lib/jenkins/workspace/warFileCreation/target/testProjectJenkins/WEB-INF
rm -rf lib'''
      }
    }

    stage('7zip the folders') {
      steps {
        sh '''cd /var/lib/jenkins/workspace/warFileCreation/target

7za a testProjectJenkins.7z testProjectJenkins
'''
      }
    }

    stage('Connect to VPN') {
      steps {
        sh '''cd /home/dkokkonos
dir

sudo openvpn --config VPNConfig.ovpn --daemon
ping -c 5 10.20.0.111

ip a
'''
      }
    }

    stage('Upload to 111') {
      steps {
        build '7zUpload'
      }
    }

    stage('Run Script') {
      steps {
        build 'Remote Script On Server'
      }
    }

    stage('Close VPN connection') {
      steps {
        sh '''ip a
sudo killall openvpn
'''
      }
    }

  }
}