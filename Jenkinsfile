pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the repository
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                // Run Maven clean and package goals
                echo 'mvn clean package'
            }
        }
    }
    
    post {
        success {
            // Send email notification on successful build
            emailext (
                subject: 'Pipeline Successful',
                body: 'The Jenkins pipeline was successfully built and deployed.',
                to: 'pavankumarsahu143@gmail.com'
            )
        }
        failure {
            // Send email notification on failed build
            emailext (
                subject: 'Pipeline Failed',
                body: 'The Jenkins pipeline failed to build or deploy.',
                to: 'pavankumarsahu143@gmail.com'
            )
        }
    }
}
