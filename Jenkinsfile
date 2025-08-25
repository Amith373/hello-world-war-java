pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'Java11'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('MySonarQube') {
                    sh 'mvn sonar:sonar -Dsonar.projectKey=hello-world-war'
                }
            }
        }
    }
}
