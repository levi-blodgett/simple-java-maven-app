pipeline {
    agent none
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
                 }
            }
        }
    }
}
