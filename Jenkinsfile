pipeline {
    agent any
    environment {
        ENV_URL = "google.com"
        SSH_CRED =credentials('SSH_CRED')
        //Replace 'PASSWD_ID' with the correct ID of the credential in Jenkins
    }
    
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'PREM', choices: ['BUN', 'GUN', 'Three'], description: 'Pick something')
    }

    tools {
        // Use the specified Maven version
        maven 'maven-3.8.6'
    }

        stages {
           stage('Stage One') {
              steps {
                 sh '''
                    echo "Stage one demo"
                    echo "${ENV_URL}"
                    mvn -v
                    hostname
                    env  # Display all environment variables
                '''
            }
        }

        stage('Parallel Demo') {
            parallel {
                stage('Stage Two') {
                    environment {
                        BATCH = "B55"
                        ENV_URL = "FB.com"
                    }
                    steps {
                        sh '''
                            echo "URL IS ${ENV_URL}"
                            echo "Batch is ${BATCH}"
                            
                        '''
                    }
                }

                stage('Stage Three') {
                    environment {
                        BATCH = "B55"
                        ENV_URL = "FB.com"
                    }
                    steps {
                        sh 'echo "Stage three demo"'
                        sh "echo URL IS ${ENV_URL}"
                        sh "echo Batch is ${BATCH}"
                        
                    }
                }
            }
        }
    }
}

// pipeline {
//     agent any
//     stages {
//         stage('Example') {
//             }
//             input {
//                 message "Should we continue?"
//                 ok "Yes, we should."
//                 submitter "alice,bob"
//                 parameters {
//                     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//                 }
//             }
//             steps {
//                 echo "Hello, ${PERSON}, nice to meet you."
//             }
//         }
//     }
// sh "${scannerHome}/bin/sonar-scanner -Dsonar.login=<YOUR_AUTH_TOKEN>"


// squ_f304202a9ba3ead7c54870494e82123f0cb20e73
