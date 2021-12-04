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
            environment {
                TOMCAT_CREDS = credentials('tomcat-credentials')
                TOMCAT_URL = credentials('tomcat-url')
            }
            steps {
                sh 'curl -s --upload-file ${WORKSPACE}/target/sparkjava-hello-world-1.0.war "http://${TOMCAT_CREDS_USR}:${TOMCAT_CREDS_PSW}@tomcat:8080/manager/text/deploy?path=/argentum-web&update=true"'
                sh 'curl -s --upload-file ${WORKSPACE}/target/sparkjava-hello-world-1.0.war "http://${TOMCAT_CREDS_USR}:${TOMCAT_CREDS_PSW}@${TOMCAT_URL}:8080/manager/text/deploy?path=/argentum-web&update=true"'
            }
        }
    }
}
