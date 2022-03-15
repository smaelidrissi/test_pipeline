pipeline {
    agent any
    environment {
        USER_MAIL = sh ( script: 'git --no-pager show -s --format=\'%ae\'', returnStdout: true ).trim()
    }
    stages{
        stage('Hello AHMED') {
            steps {
                echo 'Hello AHMED'
            }
        }
    }
    post {
        success {
            mail to: USER_MAIL , subject: 'Pipiline excuté ac succes', body: 'Test body'
        }
        failure {
            mail to: USER_MAIL , subject: 'Pipiline excuté ac error', body: 'Test body'
        }
    }
}