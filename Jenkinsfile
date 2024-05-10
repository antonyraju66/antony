pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'creating the pipeline using the Maven build automation software.'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Performing unit and integration testings using both the Citrus and the Selenium.'
            }
            post {
                success {
                    emailext attachLog: true,
                        subject: 'Testing Success for Build #${BUILD_NUMBER}',
                        from: 'antonyr1r2@gmail.com',
                        body: 'The Build #${BUILD_NUMBER} was successfully Tested using the Citrus and Selenium',
                        to: 'antonyr1r2@gmail.com'
                }
                failure {
                    emailext attachLog: true,
                        from: 'antonyr1r2@gmail.com',
                        subject: 'Testing Failed for Build #${BUILD_NUMBER}',
                        body: 'The Build #${BUILD_NUMBER} has failed in Testing using the Citrus and Selenium1',
                        to: 'antonyr1r2@gmail.com'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analysis of code is performed using the CodeScene.'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security and vulnerability scans using OWASP ZAP.'
            }
            post {
                success {
                    emailext attachLog: true,
                        subject: 'Scanning Success for Build #${BUILD_NUMBER}',
                        from: 'antonyr1r2@gmail.com',
                        body: 'The Build #${BUILD_NUMBER} has been successfully scanned using OWASP ZAP',
                        to: 'antonyr1r2@gmail.com'
                }
                failure {
                    emailext attachLog: true,
                        subject: 'Scanning Failed for Build #${BUILD_NUMBER}',
                        from: 'antonyr1r2@gmail.com',
                        body: 'The Build #${BUILD_NUMBER} has been failed in the scanning using OWASP ZAP',
                        to: 'antonyr1r2@gmail.com'
                }
            }
        }
        stage('Deployment to Staging') {
            steps {
                echo 'Deployment of the Pipleline to Amazon Web Service EC2 staging instance.'
            }
        }
        stage('Integration Testing on Staging') {
            steps {
                echo 'Running the integration testings in the staging environment.'
            }
        }
        stage('Deployment to Production') {
            steps {
                echo 'Deployment of the pipeline to Amazon Web Service EC2 production instance.'
            }
        }
    }
}