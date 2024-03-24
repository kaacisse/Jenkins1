pipeline {
    agent any
    parameters{
        string(name: 'NAME', defaultValue: 'M. Jenkins', description: 'Qui est ce ?')
        text(name: 'TEXT', defaultValue: 'un text', description:'une description')
        booleanParam(name: 'TOGGLE', defaultValue:true, description: 'true or false')
        choice( name: 'CHOICE', choices: ['un', 'deux', 'trois'], description: 'liste')
        password(name:'PASSWORD', description: 'un mot de passe')
    }
    options{
        disableConcurrentBuilds()
        timeout(time: 1, unit: "HOURS")                   
        timestamps()         
    }

    environment{
        MY_VAR = 'une variable'
        MY_NUMBER = 123
    }
    stages {
        stage('Build') {
            steps {
                echo "BRANCH_NAME : ${ env.BRANCH_NAME }"
                echo "BRANCH_IS_PRIMARY : ${ env.BRANCH_IS_PRIMARY }"    
                echo "CI : ${ env.CI }"
                echo "BUILD_NUMBER : ${ env.BUILD_NUMBER }"
                echo "JENKINS_URL : ${ env.JENKINS_URL }"
                echo "MY_VAR : ${ env.MY_VAR }"
                echo "MY_NUMBER : ${ env.MY_NUMBER }"
                sh 'printenv'

                echo "NAME : ${ NAME }"
                echo "TEXT : ${ TEXT }"
                echo "TOGGLE : ${ TOGGLE }"
                echo "CHOICE : ${ CHOICE }"
                echo "PASSWORD : ${ PASSWORD }"

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