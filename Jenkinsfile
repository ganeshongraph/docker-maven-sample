node {
    stage('SonarQube scan & Analysis') {
	withSonarQubeEnv('sonarqube') {
	sh "mvn clean verify sonar:sonar -Dsonar.projectKey=esp -Dsonar.projectName='esp'"
 }
         	 timeout(time: 10, unit: 'MINUTES') {
                 waitForQualityGate abortPipeline: true
                 }
    }
}
}
