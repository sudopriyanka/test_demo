pipeline {
    agent any
        stages {
            stage('Build') {
                steps {
                    echo 'Build Complete!'
                }
            }
            stage('Test'){
                steps{
                    echo 'Test Passed!'
                }
            }
            stage('Email Notification'){
                steps{
                    mail bcc: '', body: '''Hello! This is test mail from Jenkins Demo Job
    Thanks!!''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'priyankapandey2797@gmail.com'
                }
            }
        }
    }
    post{
        failure {  
                 mail bcc: '', body: "<b>Jenkins Build Failed!</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "priyankapandey2797@gmail.com";  
             }  
    }
}
