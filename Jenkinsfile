pipeline {
    agent none
    tools {
        maven '3.8.5'
    }
    stages {
        stage('Deploy') {
            steps {
                 agent {
                     kubernetes {
                         label 'mavenpod'
                         yamlFile 'jenkins/maven-pod.yaml'
                       }
                   }
                   container('maven') {
                   sh "mvn -B clean deploy"
		   sh "./jenkins/scripts/deliver.sh"
                 }
            }
        }
    }
}

