def pipelineName = "Multibranch folder/Mb scripted folder/Multibranch folder/"

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
				// snDevOpsSecurityResult securityResultAttributes: "{'scanner': 'Veracode', 'applicationName': 'testdummyapp'}"
				snDevOpsChange()
			}
		}

		stage('Deploy') {
			when {
				equals expected: 2, actual: 2
			}
			steps {
				echo 'Running test stage'
				//snDevOpsChange()
			}
		}		
		// stage('Deploy') {
		// 	//when {
		// 	//	branch 'main'
		// 	//}
		// 	steps {
		// 		echo 'Running deploy stage'
		// 		//error 'Failing the Deploy stage'
		// 		snDevOpsChange()
  //       script {
  //         echo 'Inside script step...'
  //         //changeRequestId = snDevOpsGetChangeNumber()
  //         changeRequestId = snDevOpsGetChangeNumber(changeDetails: """{"build_number":"${env.BUILD_NUMBER}","pipeline_name":"rama folder/child-1/child-2/fMultibranch-1234/${env.BRANCH_NAME}","stage_name":"Deploy", "branch_name":"${env.BRANCH_NAME}"}""")
  //         echo "Change Request Id without any attributes... ${changeRequestId}"
  //       }
		// 	}
		// }
	}
}
