pipeline {
    agent any
    tools {    
 // Define Gradle tool with specific version       
      gradle 'Gradle'        
 // Define JDK tool with specific version        
   //   jdk 'Java'     
 }
    
   environment {
        SONARQUBE_SERVER = credentials('sonarqube')
      //  NEXUS_CREDENTIALS = credentials('nexus-Repo')
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
                    sh 'gradle -v'
                    sh 'java --version'
                    // Build your Gradle project here
                    jdk 'java17'
                    sh './gradlew clean build'
                }
            }
        }

       
    }

    
}
