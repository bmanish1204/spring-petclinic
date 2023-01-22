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
  -Dsonar.projectKey=Petclinic_MB \\
  -Dsonar.host.url=http://172.31.23.44:9000 \\
  -Dsonar.login=sqp_d71ac5843b7a8398f3b57d869821b835e18ccd03'''
      }
    }

  }
}