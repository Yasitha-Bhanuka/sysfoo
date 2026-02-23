pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'Compiling sysfoo app…'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'Running unit tests…'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'Packaging the app…'
        sh 'mvn package -DskipTests'
      }
    }

  }
  tools {
    maven 'Maven 3.9.6'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
  triggers {
    pollSCM('* * * * *')
  }
}