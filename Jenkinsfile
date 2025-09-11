pipeline {
  agent any
  options {
    timestamps()
    buildDiscarder(logRotator(numToKeepStr: '20'))
  }
  triggers {
    pollSCM('* * * * *')
  }

  stages {
    stage('Stage 1: Build') {
      steps {
        echo 'Building project using Maven...'
      }
    }
    stage('Stage 2: Unit & Integration Tests') {
      steps {
        echo 'Running tests using JUnit and TestNG...'
      }
    }
    stage('Stage 3: Code Analysis') {
      steps {
        echo 'Analyzing code with SonarQube...'
      }
    }
    stage('Stage 4: Security Scan') {
      steps {
        echo 'Scanning for vulnerabilities using OWASP Dependency-Check...'
      }
    }
    stage('Stage 5: Deploy to Staging') {
      steps {
        echo 'Deploying to AWS EC2 Staging instance...'
      }
    }
    stage('Stage 6: Integration Tests on Staging') {
      steps {
        echo 'Running Postman tests on Staging...'
      }
    }
    stage('Stage 7: Deploy to Production') {
      steps {
        echo 'Deploying to AWS EC2 Production server...'
      }
    }
  }

  post {
    success {
      echo 'Pipeline finished successfully'
    }
    failure {
      echo 'Pipeline failed'
    }
  }
}
