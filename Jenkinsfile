pipeline{
    agent any
    stages{
        stage("build"){
            steps{
                echo "========executing build========"
            }
        }
    }

            post{
                success{
                    emailext (to: 'amadoualicisse.khaled@yahoo.fr' , body:'test body' ,subject: 'test subject jenkins')
                    echo "========executing build========"
                }
            }

}