pipeline {
  agent {
    node {
      label 'standalone-linux-slave'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        withMaven(maven: 'M3') {
          bat 'mvn clean install '
        }
        
      }
    }
    stage('Results') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml '
        archiveArtifacts 'target/*.jar'
      }
    }
  }
}
