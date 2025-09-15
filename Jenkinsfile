pipeline {
    agent { label 'Prod-release' }

    tools {
        maven 'maven3.9'
        jdk 'jdk17'
    }

    stages {
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
		
	 stage('Package') {
            steps {
                sh 'mvn package'
            }
        }	
    }

    post {
        success {
            echo 'Build succeeded on QA branch!'
        }
        failure {
            echo 'Build failed on QA branch.'
	}
     }	
   }
