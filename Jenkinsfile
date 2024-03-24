pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'build complete ....'
            }
        }
        stage('deployment production') {
            input{
                message 'Voulez-vous deployer en production ?'
                ok 'deployer'
                submitter 'admin,devops'
                submitterParameter : 'USER_SUBMIT'
                parameters{
                    string(name:'VERSION', defaultValue:'latest', description:'une version')
                }
            }
            steps {
                echo "user : ${USER_SUBMIT}"
                echo "version : ${VERSION}"
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