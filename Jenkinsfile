currentBuild.displayName = "hello-world-#"+currentBuild.number

pipeline{
    agent any
    stages{

        stage("Maven Build"){
            steps{
                sh 'mvn --version'
            }
        }

    }
}
