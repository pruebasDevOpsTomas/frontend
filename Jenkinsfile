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
     }
 }