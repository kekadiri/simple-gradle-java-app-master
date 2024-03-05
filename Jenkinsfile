pipeline {
    agent any
	tools {
	  gradle 'Gradle'
	  }

   // environment {
     //   SONARQUBE_SERVER = credentials('sonarqube')
       // NEXUS_CREDENTIALS = credentials('nexus-credentials')
    //}

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
                    sh 'gradle clean build'
                }
            }
        }

        stage('Sonar Quality Check') {
            steps {
                script {
			 withSonarQubeEnv(credentialsId: 'sonarqube') {
                        // Run SonarQube analysis
                        sh 'gradle sonarqube'
                    }
                }
            }
        }

        //stage('Deploy to Nexus') {
          //  steps {
            //    withCredentials([usernamePassword(credentialsId: 'nexus-Repo', usernameVariable: 'admin', passwordVariable: 'password')]) {
              //      script {
                        // Deploy artifacts to Nexus
                //        sh 'gradle publish -PnexusUsername=${admin} -PnexusPassword=${password}'
                  //  }
                //}
            //}
        //}
    }

    
}
