currentBuild.displayName = "hello-world-#"+currentBuild.number

pipeline{
    agent any

 environment{
     JAVA_HOME='/usr/bin/java'
     M2_HOME='/opt/apache-maven'
     MAVEN_HOME='/opt/apache-maven/bin'
     PATH='${M2_HOME}/bin:PATH'
}
    stages{

        stage("Maven Build"){
            steps{
                sh "mvn -Dorg.jenkinsci.plugins.durabletask.BourneShellScript.LAUNCH_DIAGNOSTICS=true clean test"
            }
        }

    }
}
