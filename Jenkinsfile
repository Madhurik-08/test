pipeline {
    agent any
    triggers { 
        githubPush()
    }
    stages {
        stage('Check Windows Version') {
            steps {
                bat 'ver'
                bat 'echo Current directory is: && cd'
            }
        }
        stage('Clone repository') {
            steps {
                git(
                    credentialsId: 'github-creds-id',
                    url: 'https://github.com/Madhurik-08/test',
                    branch: 'main'
                )
            }
        }

        stage('List repository contents') {
            steps {
                bat 'dir'
            }
        }

        stage('Execute commands.bat') {
            steps {
                bat 'call commands.bat'
           }
         }
    }
}
