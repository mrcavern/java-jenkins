pipeline {
	agent any
	stages {
		stage ('PRINT') {
			steps{
				sh 'echo $JOB_NAME'
			}
			stage ('WRITE'){
				sh 'echo $BUILD_NUMBER >> build_number'
			}
			stage ('READ'){
				sh 'cat build_number'
			}
		}
	}
	post{
		success{
			archiveArtifacts artifacts: 'build_number', fingerprint: true
		}
	}
}