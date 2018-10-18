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
				sh 'echo $BUILD_NUMBER >> build_number'
				sh 'ant -f build.xml'
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
			archiveArtifacts artifacts: 'build_number', fingerprint: true
			archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
		}
	}
}