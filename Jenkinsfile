pipeline {
    agent any
    tools {
        maven 'Maven 3.9.9' // Ensure this matches the Maven installation name in Jenkins
        jdk 'jdk-21'          // Ensure this matches the JDK installation name in Jenkins
    }
    environment {
        // Set any environment variables if needed
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                    archiveArtifacts artifacts: 'target/ExtentReports.html', allowEmptyArchive: true
                }
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}
