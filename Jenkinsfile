pipeline {
    agent any

    environment {
        GIT_REPO_URL = 'https://github.com/anjalidubeyy/devops-merge-conflict-demo.git'
    }

    stages {
        stage('Declarative: Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Clone Repo') {
            steps {
                script {
                    // Ensure git is available on the Jenkins agent
                    bat 'git --version' // Checking git version (optional)
                    git url: "${GIT_REPO_URL}", branch: 'main'
                }
            }
        }

        // Bypass the Build stage by commenting or removing it
        // stage('Build with Maven') {
        //     steps {
        //         script {
        //             // Running Maven build in Windows
        //             bat 'mvn clean install'
        //         }
        //     }
        // }

        stage('Test') {
            steps {
                script {
                    // Running tests with Maven
                    bat 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy the application (this is just an example, you can change it based on your deployment setup)
                    bat 'mvn deploy'
                }
            }
        }
    }

    post {
        always {
            cleanWs() // Clean workspace after build
        }
    }
}
