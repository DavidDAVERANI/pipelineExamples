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
				 sh 'echo " Env var BUILD_ID = ${env.BUILD_ID}"'
				script {
					if(params.PRE_COMPILE) {
						echo " PRE_COMPILE value = ${params.PRE_COMPILE}"
					}
				}
			}
		}
	}
}
