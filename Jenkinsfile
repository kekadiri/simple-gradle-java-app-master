pipeline {
    agent any
    tools {
    // Define Gradle tool with specific version
    gradle 'Gradle'
}
 
stages {
    stage('Build') {
        steps {
            script {
                // Encourage use of Java 17 (may not guarantee it)
                jdk 'java17'
                sh 'gradle -v'
                sh 'java --version'
                sh './gradlew clean build'
            }
        }
    }
}
}
