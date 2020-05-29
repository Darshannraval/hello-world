currentBuild.displayName = "hello-world-#"+currentBuild.number

pipeline{
    agent any

    stages{

       stage ("Git Checkout"){
       steps{
         git credentialsId: '9b3b4cf9-f14a-4432-ae37-ed975a50539b', 
         url: 'https://github.com/Darshannraval/hello-world'
            }
       } 

       stage("Maven Build"){
            steps{
             echo "stage1"
                 }
        }

    }
}
