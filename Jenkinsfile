pipeline {
 agent any
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
    sh 'CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .'
   }
  }
 }
}
