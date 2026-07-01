pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                sh '/opt/homebrew/bin/mvn compile'
            }
        }

        stage('Test') {
            steps {
                sh '/opt/homebrew/bin/mvn test'
            }
        }

        stage('Package') {
            steps {
                sh '/opt/homebrew/bin/mvn clean package'

                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }
}