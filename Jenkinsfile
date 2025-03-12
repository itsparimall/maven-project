pipeline {
  agent any
  stages {
    stage('scm checkout') {
      steps {
        git 'https://github.com/itsparimall/maven-project.git'
      }
    }

    stage('validate the code') {
      steps {

        withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MVN_HOME', mavenSettingsConfig: '', traceability: true) {
          sh 'mvn validate'
        }

      }
    }

  }
