pipeline {
    agent any

    tools {
        maven 'maven'  // This must match the Maven tool name in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/swapnilrkGit/seleniumjava.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }

    post {
        always {
            // Make sure this file path matches your actual report path (like test-output/testng-results.xml)
            junit 'test-output/testng-results.xml'
        }
    }
}
