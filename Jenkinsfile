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

        stages{
            stage('build and test'){
                matrix{
                    axes{
                        axis{
                            name 'PLATEFORM'
                            values 'linux', 'macos', 'windows'
                        }
                        axis{
                            name 'BROWSER'
                            values 'firefox','chrome','safari'
                        }
                    }
                    stages{
                        stage('build'){
                            steps{
                                echo "construire pour ${ PLATEFORM} - ${BROWSER}"
                            }
                        }
                        stage('test'){
                            steps{
                                echo "test pour ${ PLATEFORM} - ${BROWSER}"
                            }
                        }
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