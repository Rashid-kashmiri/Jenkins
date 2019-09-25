pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL} and ${env.BUILD_NUMBER} also include ${env.JOB_NAME} and  ${env.WORKSPACE}"
            }
        }
    }
}
