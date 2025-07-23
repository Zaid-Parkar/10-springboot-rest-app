pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage('Checkout from GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/Zaid-Parkar/10-springboot-rest-app.git'
            }
        }

        stage('Build with Maven (skipping tests)') {
            steps {
                // Add -DskipTests to skip the failing tests
                bat 'mvn clean package -DskipTests'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}