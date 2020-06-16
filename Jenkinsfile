pipeline {
	agent { docker { image 'node:13.8'}}
	# agent { docker { image 'maven:3.6.3'} }
	stages {
		stage ('Test'){
			steps {
				sh 'mvn --version'
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
                                echo "Test"
			 }
                }
		 stage ('Intergation Test') {
                        steps {
                                echo "Intergration test"
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
