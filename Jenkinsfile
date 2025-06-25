pipeline {
    agent any

    tools {
        maven 'maven'  // ✅ Use correct tool name from Jenkins config
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
            junit 'test-output/testng-results.xml'  // ✅ No nested node
        }
    }
}
