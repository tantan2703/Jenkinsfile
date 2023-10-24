pipeline {
    agent any
    tools {
        maven 'maven' 
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage ('Build') {
          steps {
            sh 'mvn com.diffplug.spotless:spotless-maven-plugin:apply'
            sh 'mvn clean install -DskipTests'
          }
        }
    }
}
