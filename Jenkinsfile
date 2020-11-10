pipeline {
    agent none {
        environment {
            RELEASE='20.04'
        }
        stages {
            stage('Build') {
                agent none
                environment {
                    LOG_LEVEL='INFO'
                }
                steps {
                    echo "Building release ${RELEASE} with log level ${LOG_LEVEL}..."
                }
            }
            stage('Test') {
                steps {
                    echo "Testing. I can see release ${RELEASE}, but not log level ${LOG_LEVEL}"
                }
            }
        }
    }
}
