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
        recordIssues(
          enabledForFailure: true, aggregatingResults: true, 
          tools: [java(), checkStyle(pattern: 'checkstyle-result.xml', reportEncoding: 'UTF-8')]
        )
    }
  }
}