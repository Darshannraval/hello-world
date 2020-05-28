pipeline {
  agent any

  stages {
  stage('Git Checkout'){
  git credentialsId: '55aacddd-4d9d-4122-bb9a-117d844d8ec0', 
  url: 'https://github.com/Darshannraval/hello-world'
 }
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
