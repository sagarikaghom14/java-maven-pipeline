pipeline {
    agent any

    tools {
        maven 'Maven 3.8.6' // Ensure this version is configured in Jenkins
        jdk 'JDK 11'        // Ensure this JDK version is configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from SCM
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Build the project using Maven
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run unit tests
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Package the application
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                // Simple deployment example
                sh 'echo "Deploying application..."'
                // Example of copying artifacts to a deploy location
                sh 'cp target/java-maven-pipeline-1.0-SNAPSHOT.jar C:/Users/Sagarika\\ Ghom/Downloads/Jenkins/workspace'
            }
        }
    }

    post {
        always {
            // Clean up actions
            sh 'echo "Cleaning up..."'
            // Optionally, clean up temporary files here
        }

        success {
            // Actions on successful build
            echo 'Build succeeded!'
        }

        failure {
            // Actions on failed build
            echo 'Build failed!'
        }
    }
}
