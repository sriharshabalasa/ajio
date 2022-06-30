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
          
           stage("build "){
          steps{
           sh "mvn -f ajiolux/pom.xml clean package"
           }
          }
        
        stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.127.71.50:8080/')], contextPath: '', onFailure: false, war: 'ajiolux/target/*.war' 
        }
      }
    }
    }
}
