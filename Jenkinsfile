pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
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
    stage('Deliver') {
      steps {
        sh './jenkins/scripts/deliver.sh'
        input(message: 'Finished using the web site? (Click "Proceed" to continue)', submitter: 'Proceed', submitterParameter: 'Proceed', ok: 'Proceed')
      }
    }
  }
  environment {
    CI = 'true'
  }
}