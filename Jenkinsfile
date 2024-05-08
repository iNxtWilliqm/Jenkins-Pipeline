pipeline {
    agent any
    
    stages {
        stage ('Build') {
            steps {
                echo "Compiling and packaging code using Maven"
            }
        }
        stage ('Unit and Integration Tests') {
            steps {
                echo "Running unit tests using JUnit"
                echo "Running integration tests using JMeter"
            }
            post {
                success {
                    emailext (
                        to: "williamchoi418@gmail.com",
                        subject: "Unit and Integration Tests Status Email",
                        body: "Unit and Integration Tests have passed successful!",
                    )
                }
                failure {
                    emailext (
                        to: "williamchoi418@gmail.com",
                        subject: "Unit and Integration Tests Status Email",
                        body: "Unit and Integration Tests have failed!",
                    )
                }
                always {
                    emailext (
                        to: "williamchoi418@gmail.com",
                        subject: "Unit and Integration Tests Status Email",
                        body: "Unit and Integration Tests log attached!",
                        attachLog: true
                    )
                }
            }
        }
        stage ('Code Analysis') {
            steps {
                echo "Analysing code using Checkstyle"
            }
        }
        stage ('Security Scan') {
            steps {
                echo "Scanning code security using SonarQube"
            }
            post {
                success {
                    emailext (
                        to: "williamchoi418@gmail.com",
                        subject: "Security Scan Status Email",
                        body: "Security Scan has passed successful!",
                    )
                }
                failure {
                    emailext (
                        to: "williamchoi418@gmail.com",
                        subject: "Security Scan Status Email",
                        body: "Security Scan have failed!",
                    )
                }
                always {
                    emailext (
                        to: "williamchoi418@gmail.com",
                        subject: "Security Scan Status Email",
                        body: "Security Scan log attached!",
                        attachLog: true
                    )
                }
            }
        }
        stage ('Deploy to Staging') {
            steps {
                echo "Deploying application to AWS E2 instance"
            }
        }
        stage ('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on AWS E2 instance"
            }
            post {
                success {
                    emailext (
                        to: "williamchoi418@gmail.com",
                        subject: "Integration Tests on Staging Status Email",
                        body: "Integration Tests on Staging has passed successful!",
                    )
                }
                failure {
                    emailext (
                        to: "williamchoi418@gmail.com",
                        subject: "Integration Tests on Staging Status Email",
                        body: "Integration Tests on Staging have failed!",
                    )
                }
                always {
                    emailext (
                        to: "williamchoi418@gmail.com",
                        subject: "Integration Tests on Staging Status Email",
                        body: "Integration Tests on Staging log attached!",
                        attachLog: true
                    )
                }
            }
        }
        stage ('Deploy to Production') {
            steps {
                echo "Deploying application to AWS EC2 instance"
            }
        }
    }
}