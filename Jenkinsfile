pipeline {
  agent any

  stages {
  stage('Stage 1') {
      steps {
        script {
          sh 'mvn clean install'
        }
      }
    }
  stage('Stage 2') {
      steps {
        script {
          echo 'Stage 23'
        }
      }
    }
  }
}
