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
                    emailext(
                        to: 'richisbox@gmail.com',
                        subject: 'Unit and Integration Tests Successful',
                        body: 'Unit and integration tests stage has completed successfully.',
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: 'richisbox@gmail.com',
                        subject: 'Unit and Integration Tests Failed',
                        body: 'Unit and integration tests stage has failed.',
                        attachLog: true
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
                    emailext(
                        to: 'richisbox@gmail.com',
                        subject: 'Security Scan Successful',
                        body: 'Security scan stage has completed successfully.',
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: 'richisbox@gmail.com',
                        subject: 'Security Scan Failed',
                        body: 'Security scan stage has failed.',
                        attachLog: true
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
