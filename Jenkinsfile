pipeline {
	agent any
	environment {
		dockerHome = tool 'Mydocker'
		mavenHome = tool 'mymaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		}
// agent { docker { image 'node:13.8'}}
//  agent { docker { image 'maven:3.6.3'} }
	stages {
		stage ('Test'){
			steps {
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "ID - $env.BUILD_ID"
				echo "JOB - $env.JOB_NAME"
				echo "TAG - $env.BUID_TAG"
			}
		}
		 stage ('Build') {
                        steps {
                                sh 'mvn clean compile'
				sh 'mvn package'
			 }
                }
		 stage ('Intergation Test') {
                        steps {
				script {
					dockerImage= docker.build("jamelia1303/currency-exchange-devops:${env.BUILD_TAG}")	
					docker.withRegistry('' , 'docker') {
						dockerImage.push();
						dockerImage.push('latest');
					}
				
				
			}
                }
	} 
	 post {
		always {
			echo 'I am awesome'
		}
		success {
			echo 'Hey Success'
		}
		failure {
			echo 'Fail'
		}
	}
}	
