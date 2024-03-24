pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'build complete ....'
                echo "branch : ${env.BRANCH_NAME}"
            }
        }
        stage('deployment production') {
            when {
                branch 'main'
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