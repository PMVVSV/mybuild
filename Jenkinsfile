pipeline {
    agent any
    tools {
        maven 'MVN'
    }
    stages {
        stage('01 - Git checkout'){
            steps {
                git 'https://github.com/kidh0/argentum-web'
            }
        }
        stage('02 - Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('03 - Deploy') {
            environment {
                TOMCAT_CREDS = credentials('tomcat-credentials')
                TOMCAT_URL = credentials('tomcat-url')
            }
            steps {
                sh 'curl -s --upload-file ${WORKSPACE}/target/argentum-web.war "http://${TOMCAT_CREDS_USR}:${TOMCAT_CREDS_PSW}@${TOMCAT_URL}:8080/manager/text/deploy?path=/argentum-web&update=true"'
            }
        }
    }
}
