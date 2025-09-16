pipeline {
    agent { label 'PROD-APP-RELEASE' }

    tools {
        maven 'mvn3.9'
        jdk 'JDK-17'
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
            echo 'Build succeeded for master!'
        }
        failure {
            echo 'Build failed for master.'
        }
    }
}

