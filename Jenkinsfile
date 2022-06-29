pipeline {
    agent any
        
    tools {
    maven 'maven' 
  }

    stages {
       stage("Git Checkout"){
          steps{
           git 'https://github.com/sriharshabalasa/ajio.git'
           }
          }
          
           stage("build"){
          steps{
           sh "mvn -f ajiolux/pom.xml clean package"
           }
          }
    }
}
