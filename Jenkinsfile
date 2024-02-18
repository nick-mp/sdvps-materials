pipeline {
 agent any
 tools {
  go 1.16
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
    sh 'go build -a -installsuffix nocgo -o /app .'
   }
  }
 }
}
