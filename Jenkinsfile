pipeline {
    agent any
    tools {
        maven 'MVN'
    }
    stages {
        stage('01 - Git checkout'){
            steps {
                git 'https://github.com/PMVVSV/mybuild.git'
            }
        }
        stage('02 - Package') {
            steps {
                sh 'mvn clean package'
            }
        }
         stage('03 - Deploy') {
             steps{
           deploy adapters: [tomcat9(credentialsId: 'cd17d72e-7417-4b5d-8eaa-d87df4a96609', path: '', url: 'http://20.119.42.134:8081/')], contextPath: 'java-war', war: '**/*.war'
            }
         }
    }
}
