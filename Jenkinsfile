pipeline {
    agent any

    tools {
        maven 'maven'   // 👈 This must match the name you gave above
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
