pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('Static analysis') {
      steps {
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.host.url=http://172.31.23.44:9000 \\
  -Dsonar.login=sqp_868c847dbf546e1eac64db0c5c1b5726b90906f3'''
      }
    }

  }
}