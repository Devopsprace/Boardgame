pipeline {
    agent { label 'agent-1'}
     
    tools {
        maven 'maven39'
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
        
        stage('Build') {
            steps {
              sh "mvn package"
            }
        }
    }
}
