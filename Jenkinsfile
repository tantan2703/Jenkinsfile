pipeline {
    agent any
    environment {
        JAVA_HOME = "/var/jenkins_home/tools/hudson.model.JDK/openjdk21/jdk-21.0.1"
        SCANNER_HOME = tool 'sonar'
    }
    
    tools {
        jdk 'openjdk21'
        maven 'maven'
        
    }   
    stages {
        stage('SCM') {
            steps {
                checkout scm
            }
        }
        stage('Compile') {
            steps {
              sh "mvn spotless:apply"
              sh "mvn clean install -DskipTests"
            }
        }
    }
}
    
