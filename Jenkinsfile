pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Use build automation tool Maven to compile and package code.'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Run unit tests and integration tests using Selenium.'
            }
            post {
                success {
                    echo 'Unit and Integration Tests succeeded.'
                    emailext(
                        subject: 'Unit and Integration Tests Successful',
                        body: 'The unit and integration tests stage has completed successfully. Please check the logs for details.',
                        to: 'richisbox@gmail.com',
                        attachLog: true  // Attach build log to the email
                    )
                }
                failure {
                    echo 'Unit and Integration Tests failed.'
                    emailext(
                        subject: 'Unit and Integration Tests Failed',
                        body: 'The unit and integration tests stage has failed. Please check the logs for details.',
                        to: 'richisbox@gmail.com',
                        attachLog: true  // Attach build log to the email
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyse code using SonarQube code analysis tool.'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Perform a security scan using OWASP ZAP security scanning tool.'
            }
            post {
                success {
                    echo 'Security Scan succeeded.'
                    emailext(
                        subject: 'Security Scan Successful',
                        body: 'The security scan stage has completed successfully. Please check the logs for details.',
                        to: 'richisbox@gmail.com',
                        attachLog: true  // Attach build log to the email
                    )
                }
                failure {
                    echo 'Security Scan failed.'
                    emailext(
                        subject: 'Security Scan Failed',
                        body: 'The security scan stage has failed. Please check the logs for details.',
                        to: 'richisbox@gmail.com',
                        attachLog: true  // Attach build log to the email
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploy application to staging server AWS EC2 staging environment.'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Run integration tests on the staging environment using Selenium.'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy application to production server AWS EC2 production environment.'
            }
        }
    }
}
