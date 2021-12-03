pipeline {

    agent any
    stages{
          stage('gitcheckoutstage'){
               steps{
                     git 'https://github.com/PMVVSV/mybuild.git'
                    }
       }

         stage('build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('deploy'){

            steps{

                sh '/opt/deploy.sh'
            }

            }

         }
         post {
                    success{


                   archiveArtifacts 'target/*.war'
            }
}
}
