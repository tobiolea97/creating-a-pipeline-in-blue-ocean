pipeline {
  agent none
  stages {
    stage('Build and Test') {
      agent {
        docker {
          image 'node:6-alpine'
          args '-p 3000:3000'
          network 'my_custom_network'
        }
      }
      steps {
        sh 'npm install'
        sh './jenkins/scripts/test.sh'
      }
    }
  }
}
