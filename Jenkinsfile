pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Build') {
      steps {
        withMaven(maven: 'M3', jdk: 'JDK') {
          sh 'mvn clean install'
        }

      }
    }

    stage('Results') {
      steps {
        junit 'Ajouter **/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}