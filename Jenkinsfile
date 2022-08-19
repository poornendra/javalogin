pipeline {
    agent any

    stages {
        stage('Build') {
            steps {

                // Run Maven on a Unix agent.
                sh "mvn  clean install"
  
            }
        }
		stage('Deploy to Dev'){
		steps {
		deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.214.155.191:8080/')], contextPath: 'Java app', war: '**/*.war'
		}
	}
	}
}
}
