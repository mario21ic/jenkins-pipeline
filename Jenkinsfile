pipeline {
  agent any
  options {
    ansiColor('xterm')
    timestamps()
    timeout(time: 1, unit: 'HOURS')
  }
  environment {
    ARTIFACTOR = "${env.BUILD_NUMBER}.zip"
    SLACK_MESSAGE = "Job '${env.JOB_NAME}' Build ${env.BUILD_NUMBER}"
}
  stages {
    stage("Repository") {
      steps {
          //git url: "https://github.com/mario21ic/jenkins-pipeline.git"
        checkout scm
      }
    }
    stage("Build") {
      steps {
        echo "build"
        sh "echo ${env.BUILD_NUMBER}"
        sh "echo ${env.ARTIFACTOR}"
        sh "echo ${env.SLACK_MESSAGE}"
      }
    }
    stage("Test") {
      steps {
        sh "echo tests"
      }
    }
    stage("Deploy") {
      steps {
        sh "echo deploy"
      }
    }
  } 
}
