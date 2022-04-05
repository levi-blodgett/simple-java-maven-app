pipeline {
	agent {
		kubernetes {
                	label 'mavenpod'
                	yamlFile 'jenkins/maven-pod.yaml'
                }
        }
	stages {
		stage('Deploy'){
			steps {
				container('maven') {
				        sh "mvn -B clean deploy"
        			}
			}
		}
	}
}
