pipeline {
    agent any
  stages {
    stage('Upload to aws') {
      steps {
        withAWS(region:'us-west-2', credentials: 'ci-cd-entity') {
          s3Upload(bucket:'jenkins-ci-test-hojarasca', path:'', includePathPattern:'*.html', workingDir:'.')
        }
      }
    }
  }
}