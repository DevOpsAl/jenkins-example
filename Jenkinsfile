pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                sh 'mvn clean compile'
            }
        }

        stage ('Testing Stage') {

            steps {
                sh 'mvn test'
            }
        }


        stage ('Publish Test Results') {
			steps {
						
						
			junit 'target/surefire-reports/*.xml'
			}
        }
        stage ('Execute Jar File') {
			steps{
				sh 'java -jar target/*.jar'
			}
		}
    }
}
