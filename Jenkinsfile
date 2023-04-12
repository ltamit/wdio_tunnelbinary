pipeline {
  agent any

  tools {
    nodejs "NodeJS16"
  }

  stages {
    stage('Build') {
      steps {
        sh 'npm install'
        // Set environment variables for the entire pipeline
        withEnv(['LT_USERNAME=${LT_USERNAME}', 'LT_ACCESS_KEY=${LT_ACCESS_KEY}']) {
          sh 'echo "Environment variables set for the entire pipeline"'
        }
      }
    }

    stage('Test') {
      steps {
        sh "./LT --user ${LT_USERNAME} --key ${LT_ACCESS_KEY} &"
        sh 'npx wdio run conf/local.conf.js'
      }
    }
  }
}
