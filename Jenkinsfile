pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /var/jenkins_home/.m2:/root/.m2'
            reuseNode true
        }
    }

    stages {  // ✅ stages block should be here
        stage('Test') {  // ✅ Each stage needs a name
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }

        stage('Deliver') {  // ✅ Each stage is at the same level
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}




