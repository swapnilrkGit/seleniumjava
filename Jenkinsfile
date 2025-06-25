pipeline {
    agent any

    tools {
        maven 'Maven 3.9.6'   // Replace with your Jenkins-configured Maven name
        jdk 'JDK 11'          // Replace with your Jenkins-configured JDK
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
            junit 'test-output/testng-results.xml'
        }
    }
}
