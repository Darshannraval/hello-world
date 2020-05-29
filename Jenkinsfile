currentBuild.displayName = "hello-world-#"+currentBuild.number

pipeline{
    agent any
    environment{
         PATH = "/opt/apache-maven-3.6.3/bin:$PATH"
         registry = "darshannraval"
         registryCredential = 'dockerhub_id'
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
         script{ dockerImage = docker.build registry }    
             } 
        }

  }

}
