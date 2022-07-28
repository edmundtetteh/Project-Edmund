
pipeline {
  agent any
  tools {
    maven 'MAVEN_HOME'
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8(credentialsId: 'tomcat8', path: '', url: 'http://35.175.102.199:8080/')], contextPath: null, war: '**/*.war'
        }
      }
    }
  }
}
