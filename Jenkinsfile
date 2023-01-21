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
  -Dsonar.login=sqp_bff2fea384cb01d3ec9fa9ad448753d4093c93a4'''
      }
    }

  }
}