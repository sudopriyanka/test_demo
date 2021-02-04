pipeline {
    agent any
    try{
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
    catch(err){
        stage('Email Notification'){
            steps{
                mail bcc: '', body: '${err}', cc: '', from: '', replyTo: '', subject: 'Jenkins Job Failed!', to: 'priyankapandey2797@gmail.com'
            }
        }
    }
}
