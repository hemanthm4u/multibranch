pipeline {
    agent any
    tools {
        maven "maven3.6.6"
    }
    stages {
        stage('checkout&build') {
            steps {
                git 'https://github.com/jenkinsdemorepo/mavenproject'
                sh "mvn package"
            }
        }
		
		stage('Deliver for development') {
            when {
                branch 'develop' 
            }
            steps {
                  sh "cp target/JenkinsWar.war /var/lib/tomcat9/webapps/"
            }
            }
			
		    }
}
