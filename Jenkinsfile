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
           
            steps {
               deploy adapters: [tomcat9(credentialsId: '99adb576-0d96-41a7-bff9-657e38b5f8f5', path: '', url: 'http://20.119.42.134:8081/')], contextPath: 'sparkjava-hello-world-1.0', war: '/target/sparkjava-hello-world-1.0.war'
            }
        }
    }
}
