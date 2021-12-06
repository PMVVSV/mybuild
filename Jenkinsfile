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
        stage('02 - Test') {
            steps {
                sh 'mvn clean test -Dtest=xxxxTest'
            }
        }
        stage('03 - Package') {
            steps {
                sh 'mvn clean package'
            }
        }
         stage('04 - Deploy') {
             steps{
           deploy adapters: [tomcat9(credentialsId: '5ca39a88-cd22-4dc5-92fe-19826bbcd480', path: '', url: 'http://20.119.42.134:8081/')], contextPath: 'sparkjava-hello-world-1.0/hello', war: '**/*.war'
            }
         }
    }
}
