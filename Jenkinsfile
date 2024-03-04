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

        stage('Static Code Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    script {
                        // Run SonarQube analysis
                        sh './gradlew sonarqube'
                    }
                }
            }
        }

        stage('Deploy to Nexus') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'nexus-Repo', usernameVariable: 'admin', passwordVariable: 'password')]) {
                    script {
                        // Deploy artifacts to Nexus
                        sh './gradlew publish -PnexusUsername=${admin} -PnexusPassword=${password}'
                    }
                }
            }
        }
    }

    
}
