pipeline {
    agent any

    environment {
        // Set up environment variables if required
        JAVA_HOME = '/usr/bin/java'
        MAVEN_HOME = tool 'Maven 3.6.3'
        // You can also set up other environment variables for your project here
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone your Spring Boot project repository
                // Replace the URL with your repository URL
                git branch: 'main', url: 'https://github.com/Aminebentayaa/jenkins-sonar.git'
            }
        }

        stage('Build') {
            steps {
                // Build the Spring Boot project using Maven
                // Replace 'mvn' with the actual command if Jenkins is not aware of it
                sh 'mvn clean package -DskipTests'
                // This will create a JAR file in the 'target' directory
            }
        }

        stage('Test') {
            steps {
                // Run tests (optional)
                // Add any additional testing commands here if required
                sh 'mvn test'
            }
        }

      
    }

    post {
        always {
            // Clean up after the build
            sh 'mvn clean'
        }
    }
}
