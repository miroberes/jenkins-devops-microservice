// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
//     stage('Integration Test') {
// 		echo "Integration Test"
// 	}
// }

pipeline {
    // agent any
    agent { docker 'maven:3.6.3' }
    stages {
        stage('Build') {
            steps {
                echo "Build"
                sh 'mvn --version'
            }
        }
        stage('Test') {
            steps {
                echo "Test"
            }
        }
        stage('Integration Test') {
            steps {
                echo "Integration Test"
            }
        }
        stage('Integration Test 2') {
            steps {
                echo "Integration Test 2"
            }
        }
    }
}


