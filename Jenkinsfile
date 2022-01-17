pipeline {
  agent {label 'ubuntu_slave'}
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Hello') {
      steps {
        echo "Hello $GIT_BRANCH"
        echo "New"
        echo "There is a bug"
      }
    }
  }
}