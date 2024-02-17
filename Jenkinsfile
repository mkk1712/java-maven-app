pipeline {
    agent any
    
    environment {
        SONAR_TOKEN = credentials('sonar')
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git 'https://github.com/mkk1712/java-maven-app'
            }
        }
        
        stage('Build') {
            steps {
                // Build your project (e.g., Maven, Gradle, etc.)
                sh 'mvn clean package'
            }
        }
        
        stage('SonarQube Analysis') {
            steps {
                // Run SonarQube analysis
                withSonarQubeEnv('SonarQubeServer') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
    }
    
    post {
        success {
            // If build is successful, trigger downstream jobs or perform other actions
            echo 'Build successful!'
        }
        
        failure {
            // If build fails, perform cleanup or notify stakeholders
            echo 'Build failed!'
        }
    }
}
