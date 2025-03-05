pipeline {
    agent any
    parameters {
        string(name: 'ENV', defaultValue: 'dev', description: 'choose the deployment env')
        choice(name: 'DEPLOY_TYPE', choices: ['Rolling', 'Blue-Green'], description: 'choose deploy type')
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Darshanm416/jenkins-pipeline-demo.git'
            }
        }
        stage('build') {
            steps {
                sh 'echo "building in ${ENV}"'
            }
        }
        stage('test') {
            steps {
                retry(3) {
                    sh 'echo "testing.."'
                }
            }
        }
        stage('deploy') {
            steps {
                sh 'echo "deploying... in ${DEPLOY_TYPE}."'
            }
        }
    }
    post {
        success {
            mail to: 'idarshankm@gmail.com',
                subject: "Build Succeeded: ${currentBuild.fullDisplayName}",
                body: "The build was successful. Check Jenkins for more details."
        }
        failure {
            mail to: 'idarshankm@gmail.com',
                subject: "Build Failed: ${currentBuild.fullDisplayName}",
                body: "The build failed. Check Jenkins logs for details."
        }
        always {
            slackSend channel: '#devops', message: "Build ${currentBuild.fullDisplayName} - ${currentBuild.result}"
        }
        always {
            echo "cleaning workspace"
            deleteDir()
        }
    }
}          

