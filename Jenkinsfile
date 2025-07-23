pipeline {
    agent any

    tools {
        // This should match the name of your Maven setup in Jenkins
        maven 'Maven'
    }

    stages {
        stage('Checkout from GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/Zaid-Parkar/10-springboot-rest-app.git'
            }
        }

        stage('Build with Maven') {
            steps {
                // Use 'bat' for Windows agents
                bat 'mvn clean package'
            }
        }
    }

    post {
        always {
            // This saves the built JAR file
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}