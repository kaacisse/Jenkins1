pipeline {
    agent any
    
 //   options{
 //       parallelAlwaysFailFast();
 //   }
    stages {
        stage('Build') {
            failFast true

            parallel{
                stage('build FRONTEND'){
                    steps{
                        echo 'build frontend'
                    }
                }
                stage('build BACKEND'){
                    steps{
                        echo 'build backend'
                    }
                }               
            }

        }
        stage('deployment production'){
            steps{
                echo 'deploy'
            }
        }         

    }

}