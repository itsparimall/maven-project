pipeline {
  agent any
  stages {
    stage('scm checkout') {
      steps {
        git branch: 'master', url: 'https://github.com/itsparimall/maven-project.git'
      }
    }

    stage('package the code') {
      steps {

        withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'Mvn_HOME', mavenSettingsConfig: '', traceability: true) {
          sh 'mvn clean package'
        }

      }
    }

  }
}
