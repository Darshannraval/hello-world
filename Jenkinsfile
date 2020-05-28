currentBuild.displayName = "hello-world-#"+currentBuild.number

pipeline{
    agent any
    stages{
        stage("Git Checkout"){
            steps{
     git credentialsId: '55aacddd-4d9d-4122-bb9a-117d844d8ec0', 
     url: 'https://github.com/Darshannraval/hello-world'
            }
        }
        stage("Maven Build"){
            steps{
                sh 'mvn clean test'
            }
        }
        stage("deploy-dev"){
            steps{
                sshagent(['tomcat-new']) {
                sh """
                    scp -o StrictHostKeyChecking=no target/myweb.war  ec2-user@172.31.5.176:/opt/tomcat8/webapps/
                    
                    ssh ec2-user@172.31.5.176 /opt/tomcat8/bin/shutdown.sh
                    
                    ssh ec2-user@172.31.5.176 /opt/tomcat8/bin/startup.sh
                
                """
            }
            
            }
        }
    }
}
