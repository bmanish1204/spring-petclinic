pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('Static Analysis') {
      steps {
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.host.url=http://172.31.23.44:9000 \\
  -Dsonar.login=sqp_c52e6cc77b1e507a73bd4b8bb5249a9fdef60925'''
      }
    }

  }
}