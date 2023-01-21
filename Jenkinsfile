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
  -Dsonar.login=sqp_9fe513aa07ac95c55f836ffaf6310ca952999437'''
      }
    }

  }
}