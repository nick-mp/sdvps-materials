pipeline {
 agent any
 tools {
  go 1.16
 }
 environment {
  NEXUS_VERSION = "nexus3"
  NEXUS_PROTOCOL = "http"
  NEXUS_URL = "158.160.13.3:8081"
  NEXUS_REPOSITORY = "raw-hosted"
  NEXUS_CREDENTIAL_ID = "nexus-user-credentials"
 }
 stages {
  stage('Git') {
   steps {git 'https://github.com/netology-code/sdvps-materials.git'}
  }
  stage('Test') {
   steps {
    sh 'go test .'
   }
  }
  stage('Build') {
   steps {
    sh 'go build'
   }
  }
  stage('Push') {
   steps {
    sh 'curl --fail --upload-file file.zip 'ubuntu-bionic:8081/repository/raw-hosted/my-directory/file.zip'
   }
  } 
 }
}
