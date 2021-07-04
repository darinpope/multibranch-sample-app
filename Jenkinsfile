pipeline{
    agent {label "linux"}
    options{
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr:'5', daysToKeepStr: '', numToKeepStr: '5')
        disableConcurrentBuilds()
    }
    stages{
        stage('Hello'){
            steps{
                echo "Hello"
            }
        }
        stage('cat README'){
            when {
                branch "fix-*"
            }
            steps{
                sh 'cat README.md'
            }
        }
        stage('for the PR'){
            when{
                branch 'PR-*'
            }
            steps{
                echo 'This is for PR'
            }
        }
    }
}
