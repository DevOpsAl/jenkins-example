pipeline{
	agent any
	stages {
		stage ('SCM for Java Code') {
			steps{
				git changelong: false, url: 'https://github.com/DevOpsAl/jenkins-example.git'
			}
		}
		stage ('Maven Compile') {
			steps{
				sh 'mvn clean compile'
			}
		}
		stage ('Testing Code') {
			steps{
				sh '''mvn test'''
				
			}
		}
		stage ('Package') {
			steps{
			sh 'mvn package'
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
