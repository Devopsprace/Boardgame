// This is test Pipeline auto trigger when Push in QA branch
pipeline {
    agent { label 'Prod-release' }

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
            echo 'Build succeeded on QA branch!'
        }
        failure {
            echo 'Build failed on QA branch.'
        }
    }
}
