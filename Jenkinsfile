pipeline {
    agent any
    environment {
        DEV_ENV = 'dev'
        API_DIR = './SampleStore'
    }
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
                echo 'Logging into $DEV_ENV'
                withCredentials([usernamePassword(credentialsId: 'apim_dev', usernameVariable: 'DEV_USERNAME', passwordVariable: 'DEV_PASSWORD')]) {
                    sh 'apictl login $DEV_ENV -u $DEV_USERNAME -p $DEV_PASSWORD -k'                        
                }
                echo 'Deploying to $DEV_ENV'
                sh 'apictl import-api -f $API_DIR -e $DEV_ENV -k --preserve-provider --update --verbose'
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