pipeline {
    agent any
  stages {
    stage('Upload to aws') {
      steps {
        withAWS(region:'eu-west-1', credentials: 'ci-cd-entity') {
          s3Upload(bucket:'jenkins-ci-test-hojarasca', path:'', includePathPattern:'*.html', workingDir:'.')
        }
      }
    }
  }
}