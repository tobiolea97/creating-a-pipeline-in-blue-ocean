pipeline {
  agent none
  stages {
    stage('Build and Test') {
      agent {
        docker {
          image 'node:6-alpine'
          args '-p 3000:3000'
        }
      }
      steps {
        script {
          // Run the container and specify the custom network
          docker.image('node:6-alpine').withRun("--network my_custom_network -p 3000:3000", 'npm install')
          sh './jenkins/scripts/test.sh'
        }
      }
    }
  }
}
