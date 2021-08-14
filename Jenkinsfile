pipeline {
    agent any
    environment {
        PATH = "/opt/apache-maven-3.6.3/bin:$PATH"
    }
    stages {
        stage("clone code"){
            steps{
               git credentialsId: 'gitcredentials', url: 'https://github.com/banalanidish/hello-world-3.git'
            }
        }
        stage("build code"){
            steps{
              sh "mvn clean install"
            }
        }
        stage("deploy"){
            steps{
              sshagent(['tomcatuser']) {
                 sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ubuntu@13.229.183.126:/opt/tomcat/webapps"
                 
                }
            }
        }
    }
}
