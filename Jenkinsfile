pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                // Checkout the main branch (change it to master if you use master)
                git branch: 'main', url: 'https://github.com/anjalidubeyy/devops-merge-conflict-demo.git'
            }
        }
        stage('Build with Maven') {
            steps {
                // Ensure that Maven is installed and available
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                // Run tests with Maven
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                // Add deployment steps here, e.g., deployment to cloud or server
                echo 'Deploying to environment...'
            }
        }
    }
}
