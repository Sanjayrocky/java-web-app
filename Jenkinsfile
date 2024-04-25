pipeline {
    agent any
    stages {
        stage('checkout code') {
            git branch:'main', url:'https://github.com/Sanjayrocky/java-web-app.git'
        }
        stage('buildcode') {
            sh 'mvn clean package'
        }
        stage('deploy to tomcat') {
            deploy adapters:[tomcat9(url:'http://13.233.87.11:8080', credentialsId:'tomcatcred')], war:'**/*.war'
        }
    }    
}    