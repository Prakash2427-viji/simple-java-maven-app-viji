pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /var/jenkins_home/.m2:/root/.m2'
            reuseNode true
        }
    }
    stage('Test') {
          steps {
                sh 'mvn test'
            }
         stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }  
                          
}
}
