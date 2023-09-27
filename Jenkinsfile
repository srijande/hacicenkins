pipeline {
  environment {
    imagename = "srijande/jenkins-test"
    dockerImage = ''
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/srijande/hacicenkins.git', branch: 'master', credentialsId: 'github-srijande'])

      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build imagename
        }
      }
    }
    stage('Remove Unused docker image') {
      steps{
        // sh printf($(git rev-parse --short HEAD))
        // sh "docker rmi $imagename:$BUILD_NUMBER"
        sh "docker rmi $imagename:latest"


      }
    }
  }
}
