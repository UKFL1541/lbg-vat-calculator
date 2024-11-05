pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from GitHub repository
          git branch: 'main', url: 'https://github.com/UKFL1541/lbg-vat-calculator.git'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
        steps {
            withSonarQubeEnv('sonarqube-bj') {
              sh "${scannerHome}/bin/sonar-scanner"
            }
        }
    }
  }
}