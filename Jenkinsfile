pipeline {
	agent any
	stages {
		stage ('PRINT') {
			steps{
				sh 'echo $JOB_NAME'
			}
		}
		stage ('WRITE'){
			steps{
				sh 'ant -f build.xml -v'
			}	

		}
		stage ('READ'){
			steps{
				sh 'cat build_number'
			}
		}
	}
	post{
		success{
			archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
		}
	}
}