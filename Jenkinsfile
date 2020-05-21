pipeline {
    agent any
  stages {
    stage('lint html') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to aws') {
      steps {
        withAWS(region:'us-west-2', credentials: 'ci-cd-entity') {
          s3Upload(bucket:'jenkins-ci-test-hojarasca', path:'', includePathPattern:'*.html', workingDir:'.')
        }
      }
    }
  }
}