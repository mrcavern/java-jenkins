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
	}
	post{
		success{
			archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
		}
	}
}