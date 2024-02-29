pipeline {
  agent any
  tools {
    gradle 'Gradle'
  }
  stages {
    stage('test') {
      steps {
        sh 'gradle clean build'
      }
      
    }
  }
}
