pipeline {
    agent {
        docker {
            image 'maven:3.9.2'
            args '--network=host'
        }
    }
    environment {
        DOCKER_HOST = "tcp://jenkins-docker:2376"
        DOCKER_TLS_VERIFY = "0"
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
