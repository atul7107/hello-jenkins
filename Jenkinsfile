pipeline{
  agent {
      label 'Slave_1'
  }
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
      stage("deploy-Tomcat_server"){
       steps{
         sh"""
          scp -i /home/Jenkins/.ssh/Jenkins_key_pair.pem -r /tmp/remoting.jar ubuntu@44.202.148.250:/home/ubuntu/Tomcat
          """
          }
        }
      }
   }
