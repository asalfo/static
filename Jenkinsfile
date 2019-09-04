pipeline {
     agent any
     stages {
          stage('Lint HTML'){
               steps {
                    sh 'tidy -q -e *.html'
               }
          }
          stage('Upload to AWS'){
               steps {
                       withAWS(region:'eu-west-3',credentials:'aws-static') {
                           s3Upload(file:'index.html', bucket:'asalfo-aws-pipeline', path:'index.html')
                       }
                }
            }
     }
}
