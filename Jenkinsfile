pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 80:3000'
    }
    
  }
  stages {
    stage('build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
  }
  environment {
    CI = 'true'
  }
}