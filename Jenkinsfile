pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'Maven-3.8.1'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/HALIMAELHAOUHAY/hello-maven.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh "${MAVEN_HOME}/bin/mvn clean package"
            }
        }

        stage('Test') {
            steps {
                sh "${MAVEN_HOME}/bin/mvn test"
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
