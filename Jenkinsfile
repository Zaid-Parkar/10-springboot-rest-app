pipeline {
    agent any

    tools {
        // IMPORTANT: Use the name of your Maven installation in Jenkins
        // You can find this in Manage Jenkins > Global Tool Configuration
        maven 'Maven_3.8.4'
    }

    stages {
        stage('Checkout from GitHub') {
            steps {
                // Replace this with the URL of your own GitHub repository
                git branch: 'main', url: 'https://github.com/Zaid-Parkar/10-springboot-rest-app'
            }
        }

        stage('Build with Maven') {
            steps {
                // This command cleans the project and runs the 'package' goal
                sh 'mvn clean package'
            }
        }
    }

    post {
        always {
            // This saves the JAR file produced by the build
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}