pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Darshanm416/jenkins-pipeline-demo.git'
            }
        }
        stage(''build) {
            steps {
                sh 'echo "building"'
            }
        }
        stage('test') {
            steps {
                sh 'echo "testing.."'
            }
        }
        stage('deploy') {
            steps {
                sh 'echo "deploying...."'
            }
        }
    }   
}
