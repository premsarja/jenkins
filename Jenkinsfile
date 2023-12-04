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
                      env  #just to ensure SSH_PASSWD TO SEE we updated as env env is system command to see what all env is there
                      
                   '''
            }
        }
        stage('stage two') {
            steps {
                ENV_URL="google.com"
                echo "${ENV_URL}"
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
