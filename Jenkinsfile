pipeline {
  agent {label 'linux'}
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build') {
      steps {
        sh './gradlew clean test --no-daemon'
      }
    }
  }
  post {
    always {
        junit '**/build/test-results/test/*.xml'
    }
  }
}