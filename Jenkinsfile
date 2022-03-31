pipeline {
  agent {label 'ubuntu_slave'}
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Hello') {
      when { changeRequest() }
      steps {
        echo "name of git branch $GIT_BRANCH"
        echo "This is $CHANGE_ID"
        echo "this is $CHANGE_BRANCH"
        echo "There is $CHANGE_TARGET"
      }
    }
  }
}