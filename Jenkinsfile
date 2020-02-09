pipeline {
	agent { label "kubernetes" }
	stages {
		stage ("Build") {
			steps {
				dir(WORKSPACE){
					dockerBuild steps:this
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