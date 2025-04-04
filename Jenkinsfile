pipeline {
    agent {
        label 'agent-1-lablel'
    }
    stages {
        stage('Build') {
            steps {
                    sh "echo this is build"
            }
        }
        stage('Test') {
            steps {
                    sh "echo this is test"
            }
        }
        stage('Deploy') {
            steps {
                    sh "echo this is deploy"
                    // error "this will be failed"
            }
        }
    }
    post {
        always{
            echo "thhis will run always"
            // deleteDir()
        }
        success{
            echo "this will run on success"
        }
        failure{
            echo "this will run at failure"
        }
    }
}
