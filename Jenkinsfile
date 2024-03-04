pipeline {
    agent any

    environment {
        SONARQUBE_SERVER = credentials('sonarqube')
        NEXUS_CREDENTIALS = credentials('nexus-Repo')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    // Build your Gradle project here
                    sh './gradlew clean build'
                }
            }
        }

       
    }

    
}
