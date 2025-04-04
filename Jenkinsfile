pipeline {
    agent {
        label 'agent-1-lablel'
    }
     options{
        timeout(time: 20, unit: 'SECONDS')
        disableConcurrentBuilds()
        // retry(1)
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                    echo "Hello ${params.PERSON}"
            }
        }
        stage('Deploy') {
            steps {
                    sh 'echo this is deploy'
                    // error "this will be failed"
            }
        }
        stage('Print Params'){
            steps{
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"  
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
