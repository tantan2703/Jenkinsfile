pipeline {
    agent any
    environment {
        SCANNER_HOME = tool 'sonar'
    }
    tools {
        jdk 'OpenJDK-21'
        maven 'maven3'
        
    }   

    stages {
        stage('SCM') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/tantan2703/WebGoat.git'
            }
        }
    }
    stages {
        stage('Compile') {
            steps {
               sh "mvn clean compile"
            }
        }
    }
    stages {
        stage('Compile') {
            steps {
               sh "mvn clean compile"
            }
        }
    }
     stages {
        stage('Sonarqube Analysis') {
            steps {
               withSonarQubeEnv('sonar-server') {
                   sh '''$SCANNER-HOME/bin/sonar-scanner -Dsonar.projectName=webgoat \ 
                   -Dsonar.java.binaries=. \ 
                   -Dsonar.projectKey=webgoat '''
               }
            }
        }
    }
}
