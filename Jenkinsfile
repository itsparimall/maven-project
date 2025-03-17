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

    stage('deploy the code on tomcat') {
      steps {

       sshagent(['DEVCICD']) {
        sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@44.204.18.123:/usr/share/tomcat/webapps'

}

      }
    }
  }
}
