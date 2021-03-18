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
    
    stage('Install, Test, & Build') {
      steps {
        sh '''
          npm install
          npm run test
          npm run build
        '''
      }
    } 
  }
}