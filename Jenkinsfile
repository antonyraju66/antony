pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven.'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration testings using the Citrus and Selenium.'
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
                        body: 'The Build #${BUILD_NUMBER} has failed in Testing using the Citrus and Selenium',
                        to: 'antonyr1r2@gmail.com'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code using the CodeScene.'
                echo 'Analyzing code using the CodeScene.'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security and vulnerability scans using OWASP ZAP.'
            }
            post {
                success {
                    emailext attachLog: true,
                        subject: 'Scanning Successfor Build #${BUILD_NUMBER}',
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
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to Amazon Web Service EC2 staging instance.'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running the integration tests in the staging environment.'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to Amazon Web Service EC2 production instance.'
            }
            post {
                success {
                    emailext attachLog: true,
                        subject: 'Deployment Success for Build #${BUILD_NUMBER}',
                        from: 'antonyr1r2@gmail.com',
                        body: 'The Build #${BUILD_NUMBER} has been deployed to Amazon Web Service EC2 production instance',
                        to: 'antonyr1r2@gmail.com'
                }
                failure {
                    emailext attachLog: true,
                        subject: 'Deployment Failed for Build #${BUILD_NUMBER}',
                        from: 'antonyr1r2@gmail.com',
                        body: 'The Build #${BUILD_NUMBER} has been failed in Deployment',
                        to: 'antonyr1r2@gmail.com'
                }
            }
        }
    }
}