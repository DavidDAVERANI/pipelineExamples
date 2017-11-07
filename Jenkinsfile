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
            echo " Branche name in stage level = ${params.BRNACHE_NAME}"
            echo " Env var BUILD_ID = ${env.BUILD_ID}"
            echo " Env var JOB_NAME = ${env.JOB_NAME}"
            echo " Env var JENKINS_URL = ${env.JENKINS_URL}"

			steps {
				echo 'STEP DEPLOLY ZAAMA'
				script {
					if(params.PRE_COMPILE) {
						echo " PRE_COMPILE value = ${params.PRE_COMPILE}"
					}
				}
			}
		}
	}
}
