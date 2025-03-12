pipeline {
  agent any
  stages {
    stage('scm checkout') {
      steps {
        git 'https://github.com/itsparimall/maven-project.git'
      }
    }

    stage('print your message') {
      steps {
        sh 'echo hello'
      }
    }

  }
}
