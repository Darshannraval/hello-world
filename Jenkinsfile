currentBuild.displayName = "hello-world-#"+currentBuild.number

pipeline{
    agent any
    environment{
         PATH = "/opt/apache-maven-3.6.3/bin:$PATH"
         DOCKER_TAG = "${getLatestCommitId()}"
 }

    stages{

       stage ("Git Checkout"){
       steps{
           git credentialsId: '5d557c98-95c0-4205-9b01-ccbbecd24001', 
           url: 'https://github.com/Darshannraval/hello-world'
            }
       } 

       stage("Maven Build"){
       steps{
           sh "mvn clean package"
           sh "mv target/my-app-1.0-SNAPSHOT.jar target/my-app.jar"  
            }
        }

       stage("Docker build image"){
        steps{
          withCredentials([usernamePassword(credentialsId: '5d5db4d9-53aa-439b-94eb-c6e163ed8e2a', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USER')]) {
         sh "docker login -u ${DOCKER_USER} -p ${DOCKER_PASSWORD}"
}
         sh "docker build . -t ${DOCKER_TAG} "        
       
      }

    }
}
