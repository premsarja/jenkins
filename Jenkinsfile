pipeline {
    agent any
    environment{
          ENV_URL="google.com"  
          SSH_PASSWD= credentials('SSH_PASSWD')
    }
    stages {
        stage('stage one') {
            steps {
                sh '''
                      echo stage one demo
                      echo ${ENV_URL}
                      
                   '''
            }
        }
        stage('stage two') {
            steps {
                sh "echo 'stage two demo'"
            }
        }
        stage('stage three') {
            steps {
                sh "echo 'stage three demo'"
            }
        }
    }
}
