pipeline {
	agent any
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
			}
		}
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
			}
		}
		stage('Integration test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('Package') {
			steps {
				sh "mvn package -DskipTests"
			}
		}
		stage('Build Docker image') {
			steps {
				script {
					def dockerImage = docker.build("kdemianowski/currency-exchange-devops-jenkins:{$env.BUILD_TAG}");
				}
			}
		}
		stage('Push Docker image') {
			steps {
				script{
					docker.withRegistry('', 'dockerhub'){
						dockerImage.push();
						dockerImage.push('latest');
					}
				}
			}
		}
	}
}