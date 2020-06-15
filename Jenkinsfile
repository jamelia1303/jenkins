pipeline {
	agent { docker { image 'maven:3.6.3'} }
	stages {
		stage ('Test'){
			steps {
				sh 'mvn --version'
				echo "Build"
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
