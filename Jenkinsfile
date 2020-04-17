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
	agent any
	stages {
		stage('Build') {
			steps {
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
	}

}