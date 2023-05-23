node {
    stage('SonarQube scan & Analysis') {
  	environment {
	    scannerHome = tool 'SonarQubeScanner'
  		 }
   	steps {
            withSonarQubeEnv('sonarqube') {
                sh "mvn clean verify sonar:sonar -Dsonar.projectKey=esp -Dsonar.projectName='esp'"
       		 }
         	 timeout(time: 10, unit: 'MINUTES') {
                 waitForQualityGate abortPipeline: true
                 }
    }
    stage('Test') {
        echo 'Testing....'
    }
    stage('Deploy') {
        echo 'Deploying....'
    }
}
