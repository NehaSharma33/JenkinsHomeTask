pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your version control system
                git 'https://github.com/NehaSharma33/JenkinsHomeTask.git'
            }
        }
        
        stage('Build') {
            steps {
                // Build the project using Maven
                bat 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests (assuming Maven test phase runs tests)
                bat 'mvn test'
            }
        }
    }
    
    post {
        always {
            // Clean up workspace
            cleanWs()
        }
        success {
            // This block executes only if the pipeline successfully completes
            echo 'Build and test succeeded! Ready for deployment.'
            // You may trigger deployment here
        }
        failure {
            // This block executes only if the pipeline fails
            echo 'Build and test failed! Please check the logs for errors.'
            // You may take additional actions upon build failure
        }
    }
}
