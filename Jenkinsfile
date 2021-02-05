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
    }
     post {   
         failure {  
             mail bcc: '', body: '''Hello! This is test mail from Jenkins Demo Job
Thanks!!''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job Failed!', to: 'priyankapandey2797@gmail.com'  
         }    
     }
}
