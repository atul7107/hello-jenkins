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
      stage("deploy-dev"){
       steps{
         sh"""
          scp -i /home/Jenkins/Jenkins_key_pair.pem -r /home/Jenkins/remoting.jar ubuntu@44.202.148.250:/home/ubuntu/Tomcat
          """
          }
        }
      }
   }
