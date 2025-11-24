pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git credentialsId: 'github-creds-id', url: 'https://github.com/VaishnaviPujari04/jenkins_devops_lab.git'
      }
    }

    stage('Build') {
      steps {
        echo 'Static site - no build required'
      }
    }

    stage('Deploy') {
      steps {
        // Ensure Jenkins user has permission to write to /var/www/html
        sh '''
          sudo rm -rf /var/www/html/*
          sudo cp -r * /var/www/html/
        '''
      }
    }
  }

  post {
    success {
      echo 'Deployment succeeded'
    }
    failure {
      echo 'Deployment failed'
    }
  }
}
