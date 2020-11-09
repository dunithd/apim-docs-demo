pipeline {
    agent any
 
    stages {
        stage('Checking out project from GitHub') {
            steps {
                git branch: "main",
                url: 'https://github.com/dunithd/apim-docs-demo.git',
                credentialsId: ''
            }
        }
        stage('Depolying to DEV') {
            steps {
                echo 'Deploying to DEV'
            }
        }
        stage('Depolying to PROD') {
            steps {
                echo 'Deploying to PROD'
            }
        }
    }
 
    post {
        cleanup {
            deleteDir()
            dir("${workspace}@tmp") {
                deleteDir()
            }
            dir("${workspace}@script") {
                deleteDir()
            }
        }
    }
}