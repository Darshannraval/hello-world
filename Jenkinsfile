pipeline {
  agent any

  environment{
  MAVEN_HOME=/opt/apache-maven/bin
}

  stages {
  stage('Stage 1') {
      steps {
        script {
          sh 'mvn -B deploy'
        }
      }
    }
  stage('Stage 2') {
      steps {
        script {
          echo 'Stage 3'
        }
      }
    }
  }
}
