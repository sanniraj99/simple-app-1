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
        stage('codedeploy'){
          steps {
            step([$class: 'AWSCodeDeployPublisher', applicationName: 'sample-app', deploymentGroupAppspec: false, deploymentGroupName: 'sample-app', excludes: '', iamRoleArn: '', includes: 'simple-app-1', proxyHost: '', proxyPort: 0, region: 'us-east-1', s3bucket: 'sampleapp-1', s3prefix: '', subdirectory: '', versionFileName: '', waitForCompletion: false])
           }
        }
    }
}
