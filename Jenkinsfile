pipeline {
    agent any

tools{
maven "MAVEN3"

}
    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from Git repository
                git 'https://github.com/NehaSharma33/JenkinsHomeTask.git'
            }
        }
\
       
 stage('Build') {
            steps {
                // Build the project using Maven
                sh 'mvn clean install -f pom.xml'
            }
        }

         }

    post {
        success {
            // Send email notification on successful build
            emailext (
                subject: "Build ${currentBuild.fullDisplayName} succeeded",
                body: "Build ${currentBuild.fullDisplayName} succeeded. No further action required.",
                to: "mayi.neha@gmail.com"
            )
        }
        failure {
            // Send email notification on failed build
            emailext (
                subject: "Build ${currentBuild.fullDisplayName} failed",
                body: "Build ${currentBuild.fullDisplayName} failed. Please investigate and take necessary actions.",
                to: "mayi.neha@gmail.com"
            )
        }
    }
}
