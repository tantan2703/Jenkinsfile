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
            sh 'mvn spotless:apply'
            sh 'mvn clean install -DskipTests'
          }
        }
    }
}
