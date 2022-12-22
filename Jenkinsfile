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
                git 'https://github.com/sadiqali6943/automation.git'
                script {
                    sh (/mvn clean test/)
                }

                step ([$class : 'Publisher', reportFilePattern : '**/testng-results.xml'])
            }
        }
    }
}
