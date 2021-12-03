pipeline{
  agent any
    tools{
    jdk 'myjava'
    maven 'mymvn'
    }
    stages{
       stage('gitcheckoutstage'){
         steps{
             git clone https://github.com/PMVVSV/mybuild.git
         }
       }
        stage('Build'){
          steps{
            sh 'mvn clean package'
          }
        }
        stage('Deploy'){
          steps{
            sh '/opt/deploy.sh'
          }
        }
        
    }
}
