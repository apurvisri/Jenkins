pipeline {
    agent any 
    environment {
        RELEASE='20.04'
        }
     stages {
        stage('Build') {
             agent any
             environment {
                LOG_LEVEL='INFO'
                }
              steps {
                 echo "Building release ${RELEASE} with log level ${LOG_LEVEL}..."
                }
            }
         stage('Test') {
              steps {
                 echo "Testing. I can see release ${RELEASE}..."
                }
            }
         stage('Deploy') {
             input {
               message 'Deploy?'
               ok 'Do it!'
                 parameters {
                   string(name: 'TARGET_ENVIRONMENT', defaultvalue: 'PROD', description: 'Target deployment environment')
                 }
             }
             steps {
                 echo "Deployment release ${RELEASE} to environment ${TARGET_ENVIRONMENT}"
             }
         }
        }
    post {
        always {
           echo "print whether deploy happened or not, success or failure"
        }
    }
}
