pipeline {
	agent any

	stages {
		stage ('Compile Stage') {
			when {
                // only if PRE_COMPILE is true
                expression { params.PRE_COMPILE == true }
            }
			steps {
				withMaven(maven : 'maven_3_3_9') {
					echo 'STEP COMPILE ZAAMA'
				}
			}
		}

		stage ('Testting Stage') {
			steps {
				withMaven (maven : 'maven_3_3_9') {
					echo 'STEP TEST ZAAMA'
				}
			}
		}

		stage ('Deployment Stage') {
            
			steps {
				echo 'STEP DEPLOLY ZAAMA'
				if(params.PRE_COMPILE) {
					echo " Branche name = ${params.userFlag}"
				}
			}
		}
	}
}
