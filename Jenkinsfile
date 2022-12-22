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
        stage ("checkout, Test, Build & Publish") {
            steps{
                git 'https://github.com/sadiqali6943/automation.git'
                script {
                    sh (/mvn clean install)
                }
                step ([$RootPOM: 'pom.xml', GoalsAndOptions: 'clean test'])
                step ([$class : 'Publisher', reportFilePattern : '**/testng-results.xml'])
            }
        }
    }
}
