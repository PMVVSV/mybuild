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
            sh '/var/lib/deploy.sh'
          }
        }
        
    }
}
