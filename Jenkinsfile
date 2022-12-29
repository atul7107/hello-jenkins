pipeline{
  agent any
  stages{
    stage("Git Checkout"){
      steps{
            git credentialsId: "Github_tokens", url: 'https://github.com/atul7107/hello-jenkins.git'
           }
          }
     stage("Maven Build"){
       steps{
            echo "mvn clean package"
            echo "mv target/*.war target/myweb.war"
             }
            }
      }
    }
