pipeline {
  agent {label 'linux'}
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build') {
      steps {
        sh './gradlew clean test'
      }
    }
  }
  post {
    always {
        junit 'build/reports/**/*.xml'
    }
  }
}