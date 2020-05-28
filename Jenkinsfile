currentBuild.displayName = "hello-world-#"+currentBuild.number

pipeline{
    agent any

 environment{
     JAVA_HOME='/usr/lib/jvm/java-1.8.0-openjdk-amd64/'
     M2_HOME='/opt/apache-maven'
     MAVEN_HOME='/opt/apache-maven/bin'
     PATH='${M2_HOME}/bin:{PATH}'
}
    stages{

        stage("Maven Build"){
            steps{
                sh "mvn clean test"
            }
        }

    }
}
