pipeline {
  agent any

  environment {
    RepoDockerHub = 'zdenkoo98'
    NameContainer = 'nodeapp_edit'
    Dockerhub_Credentials = credentials ('docker-user')
  }

  stages {

    stage("Build"){
      steps{
        sh "docker build -t ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} ."
      }
    }

    stage('Login to Dockerhub'){
      steps{
        sh "echo $Dockerhub_Credentials_PSW | docker login -u $Dockerhub_Credentials_USR --password-stdin"
      }
    }

    stage('Push image to Dockerhub'){
      steps{
        sh "docker push ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER}"
      }
    }


    stage('Push image to Dockerhub'){
      steps{
        sh "echo holamundo"
      }
    }

  }
}
