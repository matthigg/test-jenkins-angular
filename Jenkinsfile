pipeline {
  agent any

  stages {
    stage('Git Checkout') {
      steps {
        checkout([
          $class: 'GitSCM', 
          branches: [[name: '*/develop']],
          userRemoteConfigs: [[url: 'https://github.com/matthigg/test-jenkins-angular']]
        ])
      }
    }
    
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }
    
    stage('Test') {
      steps {
        sh 'npm run test --watch false'
      }
    }
    
    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }
  }
}