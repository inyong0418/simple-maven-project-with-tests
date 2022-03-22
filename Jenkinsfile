node {
  ckeckout scm
  stage('Build') {
    withMaven(maven: 'M3') {
      
      if (isUnix()) {
        sh 'mvn -Dmaven.test.failure.ignore clean package'
      }
      els {
        bat 'mvn -Dmaven.test.failure.ignore clean package'
      }
    }
	}
  stage('Results') {
    junit '**/target/surefire-reports/TEST-*.xml'
    archive 'target/*.jar'
  }
}
