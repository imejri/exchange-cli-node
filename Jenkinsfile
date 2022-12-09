pipeline {
    agent {
        docker {image 'node:latest'}
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm ci'
              } 
       }
        stage('Unit Test') {
            steps {
                input message: 'Execute Unit Test ?', ok: 'Execute', submitter: 'issam'
                sh 'npm test'
            }
      } 
        stage ('Build') {
            steps {
            sh "npm run build"
            }
        }
    } // stages
} // pipeline
