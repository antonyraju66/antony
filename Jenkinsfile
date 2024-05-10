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
                        subject: 'Testing Success: Build #${BUILD_NUMBER}',
                        from: 'admin@jenkin.com',
                        body: 'The Build #${BUILD_NUMBER} was successful Tested',
                        to: 'antonyr1r2@gmail.com'
                }
                failure {
                    emailext attachLog: true,
                        from: 'admin@jenkin.com',
                        subject: 'Testing Failed: Build #${BUILD_NUMBER}',
                        body: 'Failed both the tests',
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
                        subject: 'Completed security scan',
                        from: 'admin@jenkin.com',
                        body: 'Completed security scan',
                        to: 'antonyr1r2@gmail.com'
                }
                failure {
                    emailext attachLog: true,
                        subject: 'Failed security scan',
                        from: 'admin@jenkin.com',
                        body: 'Failed security scan',
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
                        subject: 'Pipeline success',
                        from: 'admin@jenkin.com',
                        body: 'Pipeline has been created successfully!',
                        to: 'antonyr1r2@gmail.com'
                }
                failure {
                    emailext attachLog: true,
                        subject: 'Pipeline failed',
                        from: 'admin@jenkin.com',
                        body: 'The pipeline has failed. Please take necessary actions.',
                        to: 'antonyr1r2@gmail.com'
                }
            }
        }
    }
}