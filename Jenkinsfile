pipeline {
    agent any
    environment{
        DEPLOY_TO = 'production'
    }
    stages {
        stage('Build') {
            steps {
                echo 'build complete ....'
            }
        }
        stage('deployment production') {
            steps {
                echo 'deploy !'
            }
        }
    }
    post{
        always{
            echo 'always !'
        }
        success{
            echo 'success !'
        }
    }
}