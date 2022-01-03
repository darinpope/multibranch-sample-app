pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '1'))
  }
  stages {
    stage('Build') {
      steps {
        echo 'build from feature branch.'
      }
    }
    stage('for the feature branch') {
      when {
         branch "feature-*"
       }
      steps {
        sh cat README.md        
      }
    }
    stage('for the PR') {
      when {
          branch "PR-*"
        }
      steps {
        //sh '''
        
        echo ' this runs for the PR branch'
        
        //'''
      }
    }
  }
  post {
    always {
        junit(
          allowEmptyResults: true, 
          testResults: '**/build/test-results/test/*.xml'
        )
    }
  }
}
