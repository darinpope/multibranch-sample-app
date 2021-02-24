pipeline {
  agent {label "linux"}
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
    disableConcurrentBuilds()
  }
  stages {
    stage('Hello') {
      steps {
        echo "hello"
      }
    }
    stage('for the fix branch') {
      when {
        branch "fix-*"
      }
      steps {
        sh '''
          cat README.md
        '''
      }
    }
    stage('for the PR') {
      when {
        branch 'PR-*'
      }
      steps {
        echo 'this only runs for the PRs'
      }
    }
  }
}
