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
                   sh "mvn -B clean deploy:deploy-file \
		   -Durl=artifactregistry://us-east1-maven.pkg.dev/adt-demo-345918/maven \
		   -DpomFile=/var/jenkins_home/workspace/example-maven-app-2/pom.xml -Dfile=/var/jenkins_home/.m2/repository/com/mycompany/app/my-app/1.0-SNAPSHOT/my-app-1.0-SNAPSHOT.jar"
                 }
            }
        }
    }
}

