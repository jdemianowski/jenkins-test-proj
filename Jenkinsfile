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
				echo "Test"
				echo "Integration test"
			}
		}
	}
}