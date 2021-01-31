// node {
// 	stage('Build') {
// 		echo 'Build'
// 	}
// 	stage('Test') {
// 		echo 'Test'
// 	}
//     stage('Integration Test') {
// 		echo 'Integration Test'
// 	}
// }

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
                echo "$PATH"
                echo "$env.BUILD_ID"
                echo "$env.BUILD_NUMBER"
                echo "$env.BUILD_TAG"
            }
        }
        stage('Compile') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Integration Test') {
            steps {
                sh 'mvn failsafe:integration-test failsafe:verify'
            }
        }
//        stage('Build docker image') {
//            steps {
//                docker build -t allforsaledocker/currency-exchange-basic:0.0.1.SNAPSHOT
//            }
//        }
//        stage('Push docker image') {
//            steps {
//                sh 'mvn failsafe:integration-test failsafe:verify'
//            }
//        }
    }
}


