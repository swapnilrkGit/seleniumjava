pipeline {
    agent any

    tools {
        maven 'Maven' // Match this with name given in Global Tool Configuration
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
            junit 'test-output/testng-results.xml' // Adjust this if your reports are elsewhere
        }
    }
}
