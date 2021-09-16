pipeline {
    agent any
    environment {
        PATH = "/opt/maven/apache-maven-3.8.2/bin:$PATH"
    }
    stages {
        stage("clone code"){
            steps{
               git branch: 'feature-branch01', url: 'https://github.com/mukkerashiva/hello-world-3.git'
            }
        }
        stage("build code"){
            steps{
              sh "mvn clean install"
            }
        }
        
                 
                
            
        }
    }

