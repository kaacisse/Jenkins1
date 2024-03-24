pipeline {
    agent any
    environment{
        DEPLOY_TO = 'production'
    }
    stages {
        stage('Build') {
            steps {
                echo 'build complete ....'
                sh 'printenv'
            }
        }
        stage('deployment production') {
            when {
                branch "origin/main"
            }
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