pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }
  }
  stages {
    stage('Build') {
      steps {
        script {
          def customNetwork = 'my_custom_network'
          def dockerOptions = "--network ${customNetwork} -p 3000:3000"
          
          docker.image('node:6-alpine').withRun(dockerOptions, 'npm install')
          sh './jenkins/scripts/test.sh'
        }
      }
    }
  }
}
