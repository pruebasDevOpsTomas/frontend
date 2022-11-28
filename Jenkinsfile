pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 echo 'Building...'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'talejandro97.atlassian.net', branch: 'TM-3'
                 }
             }
         }
         stage('Deploy - Staging') {
             when {
                 branch 'TM-3'
             }
             steps {
                 echo 'Deploying to Staging from TM-3...'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'us-stg-1', environmentName: 'us-stg-1', environmentType: 'staging'
                 }
             }
         }
     }
 }