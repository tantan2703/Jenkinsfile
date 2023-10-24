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
        stages {
            stage('Compile') {
                steps {
                   sh "mvn clean compile"
                }
            }
             stage('Compile') {
                steps {
                   sh "mvn clean compile"
                }
            }
            stage('Sonarqube Analysis') {
            steps {
               withSonarQubeEnv('sonar-server') {
                   sh '''$SCANNER-HOME/bin/sonar-scanner -X -Dsonar.host.url=http://10.0.2.15:9000 ******** -Dsonar.projectKey=webgoat -Dsonar.projectName=webgoat -Dsonar.language=java -Dsonar.projectVersion=1.0 "-Dsonar.sources=/var/jenkins_home/workspace/Scan Web Goat" -Dsonar.java.binaries=target -Dsonar.exclusions=**/*.ts "-Dsonar.projectBaseDir=/var/jenkins_home/workspace/Scan Web Goat" '''
               }
            }
        }
    }
}
