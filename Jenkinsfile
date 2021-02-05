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
        stage('SonarQube Analytics') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.8.0.2131:sonar'
                }
            }
        }
        stage('Quality Gate'){
            steps{
                waitForQualityGate abortPipeline: true
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
