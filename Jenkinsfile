pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat "mvn clean compile"
            }
        }
        stage('Test') {
            steps {
                bat "mvn test"
            }
        }
        stage('Deploy') {
            steps {
                bat "mvn package"                
            }
        }       
    }
	stage('SonarQube Scan') {
            steps {
                withSonarQubeEnv('MySonarQube') {
                    bat "mvn sonar:sonar -Dsonar.token=sqa_75fcf88012ef93e2b6774410b4b44009d4f7d6ca"
                }				
            }
        }	
}