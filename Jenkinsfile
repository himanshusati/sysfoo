pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'building....'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'testing....'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'packaging....'
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.war'
        archiveArtifacts 'target/*war'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
}