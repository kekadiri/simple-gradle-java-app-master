pipeline {
    agent any
    tools {
    // Define Gradle tool with specific version
    gradle 'Gradle'
}
 
stages {
    stage ('Build gradle') {
        steps {
            sh 'gradle clean build'
        }
    }
}
}
