def changeRequestId = "defaultChangeRequestId"
def pipelineName = "Pipeline_snDevOpsGetChangeNumber"

pipeline {
	agent any
	tools {
		maven "Maven"
	}
	stages {
		stage('Build') {
			when {
				equals expected: 2, actual: 2
			}
			steps {
				echo 'Running build stage'
			}
		}
		stage('Test') {
			when {
				equals expected: 2, actual: 2
			}
			steps {
				echo 'Running test stage'
				// error 'Failing the Test stage'
			}
		}
		stage('Deploy') {
			//when {
			//	branch 'main'
			//}
			steps {
				echo 'Running deploy stage'
				//error 'Failing the Deploy stage'
				snDevOpsChange()
        script {
          echo 'Inside script step...'
          changeRequestId = snDevOpsGetChangeNumber()
          //changeRequestId = snDevOpsGetChangeNumber(changeDetails: """{"build_number":"${env.BUILD_NUMBER}","pipeline_name":pipelineName,"stage_name":"${stageName}"}""")
          echo "Change Request Id without any attributes... ${changeRequestId}"
        }
			}
		}
	}
}
