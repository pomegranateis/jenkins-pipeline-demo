pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/pomegranateis/jenkins-pipeline-demo.git', branch: 'main'
            }
        }
        stage('Use Credentials') {
            steps {
                withCredentials([usernamePassword(credentialsId: '4674', 
                                                 usernameVariable: 'USER', 
                                                 passwordVariable: 'PASS')]) {
                    sh '''
                      echo "Username is: $USER"
                      # Use $PASS in a command that requires authentication, but avoid echoing it directly
                    '''
                }
            }
        }
    }
}
