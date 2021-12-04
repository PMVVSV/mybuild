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
       stage('Exit from container'){
          steps{
            sh 'exit'
          }
        }
      stage('Deploy'){
          steps{
            sh '/opt/deploy.sh'
          }
        }
        
    }
}
