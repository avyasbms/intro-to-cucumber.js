pipeline {
  agent any
  stages {
    stage('Build Project') {
      steps {
        sh 'npm install'
      }
    }
    stage('Execute Simple Test') {
      steps {
        parallel(
          "Execute Simple Test": {
            sh 'npm run-script  simple'
            
          },
          "Background": {
            sh 'npm run-script  background'
            
          },
          "run test datatable": {
            sh 'npm run-script  datatable'
            
          },
          "run test world": {
            sh 'npm run-script world'
            
          },
          "Run events tests": {
            sh 'npm run-script events'
            
          }
        )
      }
    }
    stage('Living Document') {
      steps {
        livingDocs()
      }
    }
  }
}