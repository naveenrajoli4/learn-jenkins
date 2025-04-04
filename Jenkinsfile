pipeline {
    agent {
        label 'agent-1-lablel'
    }
     options{
        timeout(time: 100, unit: 'SECONDS')
        disableConcurrentBuilds()
        // retry(1)
    }
    stages {
        stage('Build') {
            steps {
                    sh 'echo this is build'
                    sh 'sleep 10'
            }
        }
        stage('Test') {
            steps {
                    sh 'echo this is test'
            }
        }
        stage('Deploy') {
            steps {
                    sh 'echo this is deploy'
                    // error "this will be failed"
            }
        }
    }
    post {
        always{
            echo 'this will run always'
            deleteDir()
        }
        success{
            echo 'this will run on success'
        }
        failure{
            echo 'this will run at failure'
        }
    }
}
