pipeline {
    agent any
    parameters {
        string(name: 'ENV', defaultValue: 'dev', description: 'choose the deployment env')
        choice(name: 'Deploy_type', choices: ['Rolling', 'Blue-Green'], description: 'choose deploy type')
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Darshanm416/jenkins-pipeline-demo.git'
            }
        }
        stage('build') {
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
