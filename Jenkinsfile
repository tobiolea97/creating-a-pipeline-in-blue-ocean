pipeline {
    agent {
        docker {
          image 'node:6-alpine'
          args '-p 3000:3000'
        }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}
