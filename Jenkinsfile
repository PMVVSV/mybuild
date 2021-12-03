pipeline{
  agent any
    tools{
    jdk 'myjava'
    maven 'mymvn'
    }
    stages{
       stage('gitcheckoutstage'){
         steps{
             git 'https://github.com/PMVVSV/mybuild.git'
         }
       }
        stage('Build'){
          steps{
            sh 'mvn clean package'
          }
        }
        stage('Deploy'){
          steps{
            sh 'docker cp 8f81b4ba6a37:/var/jenkins_home/workspace/pipeline/target/sparkjava-hello-world-1.0.war /opt/tomcat/webapps'
          }
        }
        
    }
}
