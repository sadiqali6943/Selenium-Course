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
                step {
                    sh (/mvn -version/)
                    sh (/mvn clean install)
                }

                step ([$class : 'Publisher', reportFilePattern : '**/testng-results.xml'])
            }
        }
    }
}
