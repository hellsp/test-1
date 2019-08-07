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
        sh 'npm install'
      }
    }
    stage('Test') {
      environment {
        CI = 'ture'
      }
      steps {
        sh 'echo "This is a test - `date`"'
      }
    }
    stage('Deliver') {
      steps {
        sh 'echo "This is a Deliver - `date`"'
        input 'Finished using the web site? (Click "Proceed" to continue)'
        sh 'echo "This is a kill.sh - `date`"'
      }
    }
  }
}