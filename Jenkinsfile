// SCRIPTED

// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo "Test"
// 	}
// }


// node {
// 	echo "Build"
// 	echo "Test"
// 	echo "Test"
// }


// DECLARATIVE

pipeline {
	// agent any
	agent {
		docker {
			image 'maven:3.6.3'
		}
	}
	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration test') {
			steps {
				echo "Integration test"
			}
		} 
	}
	post {
			always {
				echo "Always print this"
			}
			success {
				echo "Success"
			}
			failure {
				echo "Failure"
			}
			changed {
				echo "The status has changed in comparison to the previous build"
			}
		}

}