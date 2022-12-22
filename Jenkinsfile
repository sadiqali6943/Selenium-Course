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
        stage ("checkout, Build & Publish") {
            steps{
                git 'https://github.com/sadiqali6943/automation.git'
                script {
                    sh (/mvn -version/)
                    sh (/mvn clean install)
                }

                step ([$class : 'Publisher', reportFilePattern : '**/testng-results.xml'])
            }
        }
    }
}
