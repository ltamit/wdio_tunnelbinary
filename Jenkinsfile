pipeline {

  agent any

  tools {
    nodejs "NodeJS16"
  }

  stages {
    stage('Build') {
      steps {
        // One or more steps need to be included within the steps block.
        //sh 'curl -O https://downloads.lambdatest.com/tunnel/v3/mac/64bit/LT_Mac.zip'
        //sh 'unzip LT_MAC.zip'
        sh 'npm install'
        sh 'export LT_USERNAME=${LT_USERNAME}'
        sh 'export LT_ACCESS_KEY=${LT_ACCESS_KEY}'

      }

    }

    stage('Test') {
      steps {
        // One or more steps need to be included within the steps block.

        
        //sh "./LT  --user ${LT_USERNAME} --key ${LT_ACCESS_KEY} &"
        sh 'npm run local'
      }
    }

  }
}
