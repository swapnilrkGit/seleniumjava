pipeline {
    agent any

    tools {
        maven 'Maven'
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
            // ✅ This ensures `junit` has access to workspace context
            node {
                junit 'test-output/testng-results.xml'
            }
        }
    }
}
