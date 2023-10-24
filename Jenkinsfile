pipeline {
    agent any
    environment {
        JAVA_HOME = "/var/jenkins_home/tools/hudson.model.JDK/openjdk21/jdk-21.0.1"
        SCANNER_HOME = tool 'sonar'
    }
    tools {
        jdk 'openjdk21'
        maven 'maven3'
        
    }   
    stages {
        stage('SCM') {
            steps {
                checkout scm
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/tantan2703/WebGoat.git'
            }
        }
        stage('Compile') {
            steps {
                sh "mvn spotless:aplly"
                sh "mvn clean install -DskipTests"
            }
        }
    }
}
    
