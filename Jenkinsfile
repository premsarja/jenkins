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
            environment {
                BATCH = "B55"
                ENV_URL = "FB.com"
            }
            steps {
                sh '''
                echo batch  is "${BATCH}"
                echo URL IS "${ENV_URL}"

                '''
            }
        }
        stage('stage three') {
            steps {
                sh "echo stage three demo"
            }
        }
    }
}