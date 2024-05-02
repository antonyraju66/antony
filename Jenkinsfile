pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven."
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit and integration testings using the Citrus and Selenium."
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Analyzing code using the CodeScene."
            }
        }
        stage('Security Scan') {
            steps {
                echo "Performing security and vulnerability scans using OWASP ZAP."
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to Amazon Web Service EC2 staging instance."
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running the integration tests in the staging environment."
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to Amazon Web Service EC2 production instance."
            }
        }
    }
    post {
        success {
            mail bcc: 's221471405@deakin.edu.au',
                cc: 'antony.raju66@gmail.com',
                from: 'Jenkins_admin@jenkin.com',
                replyTo: 'Jenkins_admin@jenkin.com',
                subject: "Success: Build #${BUILD_NUMBER}",
                body: "The Build #${BUILD_NUMBER} was successful. See attachment for more details.",
                attachLog: true
        }
        failure {
            mail bcc: 's221471405@deakin.edu.au',
                cc: 'antony.raju66@gmail.com',
                from: 'Jenkins_admin@jenkin.com',
                replyTo: 'Jenkins_admin@jenkin.com',
                subject: "FAILED: Build #${BUILD_NUMBER}",
                body: "The Build #${BUILD_NUMBER} has failed. See attachment for more details.",
                attachLog: true
        }
    }
}
