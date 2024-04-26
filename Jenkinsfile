pipeline {
    agent any
    stages {
        stage('Clone Repo') {
          steps {
            git branch: 'main',
            url: 'https://github.com/sanniraj99/simple-app-1.git'
          }
        }
        stage('zip file') {
          steps {
            sh 'zip -r $Sample.zip /var/lib/jenkins/workspace/simple-app-1'
          }
        }
        stage('upload to s3') {
          steps {
            sh 'aws s3 cp $Sample.zip s3://sampleapp-1/'
          }
        }
    }
}
