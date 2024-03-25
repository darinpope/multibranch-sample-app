pipeline {
  agent {
    kubernetes {
      yaml '''
        apiVersion: v1
        kind: Pod
        spec:
          containers:
          - name: maven
            image: maven:alpine
            command:
            - cat
            tty: true
        '''
    }
  }
  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh 'mvn -version'
        }
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
        branch "PR-*"
      }
      steps {
        echo "This only runs for the PRs"
      }
    }
  }
}
