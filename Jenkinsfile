pipeline {
  agent any
  stages {
    stage('Check file 1') {
      steps {
        sh 'cat file-1.txt'
      }
    }
    stage('Check file 2') {
      steps {
        sh 'cat file-2.txt'
      }
    }
    stage('Install dependencies') {
      steps {
        sh 'npm install -d'
      }
    }
    stage('Run test cases') {
      steps {
        sh '''export JUNIT_REPORT_PATH=./test-results.xml
npx mocha --reporter mocha-jenkins-reporter'''
      }
    }
  }
  post {
    always {
      junit 'test-results.xml'

    }

  }
}