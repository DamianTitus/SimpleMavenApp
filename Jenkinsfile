pipeline {
    agent any
    tools {
        maven 'Maven'
    }   
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/DamianTitus/SimpleMavenApp.git'
            }
        }     
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Run Application') {
            steps {
                sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
            }
        }
    }   
    post {
        success {
            echo 'successful'
        }
        failure {
            echo 'fail'
        }
    }
}
