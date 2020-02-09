pipeline {
	agent { label "kubectl" }
	stages {
		stage ("Build") {
			steps {
				dir(WORKSPACE){
					//dockerBuild steps:this
                    sh 'echo skip'
				}
			}
		}
		stage ('Manifest Update') {
			steps {
				dir(WORKSPACE){
					manifestUpdate steps:this
				}
			}
		}
		stage("Kubernetes Deploy"){
			steps {
				dir(WORKSPACE){
					kubeApply steps:this
				}
			}
		}
	}
}