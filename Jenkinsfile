pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Build stage: Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Test stage: JUnit, TestNG'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Code Analysis stage: SonarQube, Checkmarx'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security Scan stage: OWASP ZAP, Nessus'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploy to Staging stage: AWS EC2'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Integration Tests on Staging stage'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production stage: AWS EC2'
            }
        }
    }
    post {
        success {
            emailext(
                subject: 'Pipeline Successful',
                body: 'The Jenkins pipeline has completed successfully.',
                to: 'madhushihidellarachchi@gmail.com',
                attachLog: true
            )
        }
        failure {
            emailext(
                subject: 'Pipeline Failed',
                body: 'The Jenkins pipeline has failed. Please check the logs.',
                to: 'madhushihidellarachchi@gmail.com',
                attachLog: true
            )
        }
    }
}
