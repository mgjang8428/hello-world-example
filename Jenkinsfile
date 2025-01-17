pipeline {
  agent {
    node {
      label 'built-in'
    }

  }
  stages {
    stage('Build') {
      steps {
        withMaven(jdk: 'M3') {
          sh 'mvn clean install'
        }

      }
    }

    stage('Result') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}