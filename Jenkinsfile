pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Task: Build and compile code using a build automation tool."
                echo "Tool: Maven"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Task: Run unit tests and integration tests."
                echo "Tools: JUnit for Unit Tests, Selenium for Integration Tests."
            }
            post {
                always {
                    emailext(
                        to: 'manish1111maheshwari@gmail.com',
                        subject: "Jenkins Pipeline: Test Stage - ${currentBuild.currentResult}",
                        body: "The Unit and Integration Tests stage has completed. Please find the attached logs.",
                        attachLog: true,
                        compressLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Task: Analyse the code and ensure it meets industry standards."
                echo "Tool: SonarQube"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Task: Perform a security scan to identify vulnerabilities."
                echo "Tool: OWASP ZAP"
            }
            post {
                always {
                    emailext(
                        to: 'manish1111maheshwari@gmail.com',
                        subject: "Jenkins Pipeline: Security Scan Stage - ${currentBuild.currentResult}",
                        body: "The Security Scan stage has completed. Please find the attached logs.",
                        attachLog: true,
                        compressLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Task: Deploy application to staging server."
                echo "Tool: Ansible / AWS CLI"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Task: Run integration tests on the staging environment."
                echo "Tool: Selenium"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Task: Deploy application to production server."
                echo "Tool: Ansible / AWS CLI"
            }
        }
    }
}
