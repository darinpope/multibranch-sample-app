pipeline{
    agent {label "linux"}
    options{
        buildDiscarder logRotator(atifactDaysToKeepStr: '', actifactNumToKeepStr:'5', daysToKeepStr: '', numToKeepStr: '5')
        disableConcurrentBuilds()
    }
    stages{
        stage('Hello'){
            steps{
                echo "Hello"
            }
        }
    }
}