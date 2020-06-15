pipeline {
	agent any
	stages {
		stage ('Test'){
			steps {
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
