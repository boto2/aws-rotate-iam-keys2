pipeline {
    agent {label 'aws-node2'}
    stages {
        stage('Rotate keys') {
            steps {
                sh '''
                echo "JENKINS_CREDENTIAL_DESCRIPTION=${JENKINS_CREDENTIAL_DESCRIPTION}"
                echo "AWS_USER_TO_UPDATE=${AWS_USER_TO_UPDATE}" 
                python rotate_iam_keys.py --jenkins-server "${JENKINS_SERVER}" --jenkins-user "${JENKINS_USER}" --jenkins-password "${JENKINS_PASSWORD}" --credentials-description "${JENKINS_CREDENTIAL_DESCRIPTION}" --aws-user-to-update "${AWS_USER_TO_UPDATE}"
                '''
            }
        }
    }
}