pipeline {
    agent any
    environment{
          ENV_URL="google.com"  
          SSH_PASSWD= credentials('SSH_PASSWD')
    }
    // triggers{ cron('*/1 * * * 1-5') }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    tools {
        maven maven-3.9.6
    } 
    stages {
        stage('stage one') {
            steps {
                sh '''
                      echo stage one demo
                      echo ${ENV_URL}
                      mvn clean
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
                echo URL IS "${ENV_URL}"
                echo batch  is "${BATCH}"
                '''
            }
        }
        stage('stage three') {
            environment {
                BATCH = "B55"
                ENV_URL = "FB.com"
            }
            steps { 
               sh 'echo "stage three demo"'
               sh "echo URL IS ${ENV_URL}"
               sh "echo batch is ${BATCH}"

            }
        }
    }
}