pipeline {
    agent {
        docker {
            image 'maven:3.9.2'
            args '-u root -v /var/jenkins_home/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
