pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '1'))
  }
  stages {
    stage('Build') {
      steps {
        //sh '''
        
        echo 'testing webhooks'
        echo 'build multibranch pipeline here.'
        
        //'''
      }
    }
    stage('for the feature branch') {
      steps {
        when {
          branch "feature-*"
        }
      }
    }
    stage('for the PR') {
      steps {
        //sh '''
        when {
          branch "PR-*"
        }
        
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
