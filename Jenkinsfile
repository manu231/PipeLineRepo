pipeline {
	agent any
	stages {
	    	stage ('git check') {
		steps {
		echo "connected to git hub and fetching files"
		git credentialsId: '2b33c230-68e2-44e0-bcd2-e443594169a5', url: 'https://github.com/manu231/PipeLineRepo'
		}

		}
		stage ('build') {
		steps {
		echo "successfully built"
		bat label: '', script: 'Build.bat'
		}

		}

		stage ('junit') {
		steps {
		echo "Unit test run successfully "
		bat label: '', script: 'Unit.bat'
		}

		}

		stage ('qulity gate ') {
		steps {
		echo "sonar cube validations successfully completed"
		bat label: '', script: 'Quality.bat'
		}

		}


		stage ('deploy ') {
		steps {
		echo "deployed successfully completed"
		bat label: '', script: 'Deploy.bat'
		}

		}

	}
	post {
		always{
			echo "this will always run"
		
		}
		
		success {
		echo "this will run only if successful"
		
		}
		
		failure {
		 echo "this will run only if any of the stage is  failed"
	
		}
	
	    unstable {
		echo "this will run only if run is marked as unstable"
		
		}
	    
		changed {
		echo "this will run if the state of the pipeline is changed"
		echo "example previous success now failure or previous failure now success"
		
		}
	}
}
