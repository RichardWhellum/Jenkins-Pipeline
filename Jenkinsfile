pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Use a build automation tool Maven to compile and package code.'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Run unit tests and integration test using Selenium'
            }            
            post {
                always {
                    mail to: 'rwhellum@deakin.edu.au',
                    subject: 'Test Stage Successful',
                    body: 'The test stage has completed successfully. Please check the logs for details.'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyse code using SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Perform a security scan using OWASP ZAP'
            }            
            post {
                always {
                    mail to: 'rwhellum@deakin.edu.au',
                    subject: 'Test Stage Successful',
                    body: 'The test stage has completed successfully. Please check the logs for details.'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploy application to staging server AWS EC2'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Run integration tests on the staging environment using Selenium'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy application to production server AWS EC2'
            }
        }
    }
}
