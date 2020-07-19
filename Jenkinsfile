

// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 	echo "Test"
// }
// }
// ##############################################

// // SCRIPTED 
// node{

// 	echo "Build"
// 	echo "Test"
// 	echo "Integration Test"
// }
// ##############################################
// DECLARATIVE
pipeline{
	agent any
	// agent any
	// agent { docker { image 'maven:3.6.3'} }
	// agent { docker { image 'node:14.5.0'} }

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		nodeHome = tool 'myNodeJs'
		PATH = "$dockerHome/bin:$mavenHome/bin:$nodeHome/bin:$PATH"
	}
	// agent { docker { image 'maven:3.6.3'} }
	stages{
		stage('Build'){
			steps{
				sh 'node --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Test'){
			steps{
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"
			}
		}
	}
	post{
		always{
			echo 'Im awesome. I run always'
		}
		success{
			echo 'I run when you are successful'
		}
		failure{
			echo 'I run when you fail'
		}
		// changed{ echo ' change of build status'}
	}


}