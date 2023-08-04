pipeline {
    agent any



    stages {
        stage('Checkout') {
            steps {
                // Clone your Spring Boot project repository
                // Replace the URL with your repository URL
                git branch: 'main', url: 'https://github.com/Aminebentayaa/jenkins-sonar.git'
            }
        }
        
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonar') {
                    sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Build') {
            steps {
                // Build the Spring Boot project using Maven
                // Replace 'mvn' with the actual command if Jenkins is not aware of it
                sh 'mvn clean package install'
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

   
}
