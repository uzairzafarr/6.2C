pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Using Maven to build the code"
            }
           
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Unit and Integration Testing using JS"
            }

              post {
                success {
                        mail to: "uzairali998@gmail.com",
                        subject: "Unit and Intergation Subject",
                        body: "Unit and integration Successed"
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Use tools like SonarQube for code analysis"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Using OWASP ZAP for security scanning"
            }

             post {
                success {
                        mail to: "uzairali998@gmail.com",
                        subject: "Security Scan Subject",
                        body: "Security Scan Successed"
                          }
                }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Using tools like AWS CLI to deploy to staging server"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Using Selenium to run integration tests on staging"
            }
              post {
                success {
                        emailext (to: 'uzairali998@gmail.com',
                        attachLog: true,
                        body: 'Integration Tests Staging Deploy',
                        subject: 'Deployment')
                         }
                }
        }
        stage('Deploy to Production') {
            steps {
                echo "Using AWS CLI to deploy to a production server"
            }
        }
    }
}
