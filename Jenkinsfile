pipeline{
    agent{
        node{
            label 'master'
        }
    }

    options{
        timestamps ()
    }

    stages{
        stage ("checkout, Test & Publish") {
            steps{
                checkout scm
                script {
                    sh (/mvn clean install/)
                }

                step ([$class : 'Publisher', reportFilePattern : '**/testng-results.xml'])
            }
        }
    }
}
