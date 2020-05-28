currentBuild.displayName = "hello-world-#"+currentBuild.number

pipeline{
    agent any

 environment{
     JAVA_HOME='/usr/lib/jvm/java-1.8.0-openjdk-amd64/'
     M2_HOME='/opt/apache-maven'
     MAVEN_HOME='/opt/apache-maven/bin'
     PATH='${M2_HOME}/bin:${PATH}'
}
    stages{
       stage ("Git Checkout"){
       steps{
         git credentialsId: '9b3b4cf9-f14a-4432-ae37-ed975a50539b', 
         url: 'https://github.com/Darshannraval/hello-world'
       }
} 

        stage("Maven Build"){
            steps{
                sh label: '', script: 'mvn clean test'
            }
        }

    }
}
