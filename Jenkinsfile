pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'this is the build job'
        sh 'npm install'
      }
    }

    stage('test') {
      steps {
        echo 'this is the second job'
        sh 'npm test'
      }
    }

    stage('package') {
      steps {
        echo 'this is the third job'
        sh 'npm run package'
        sleep 7
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this is the way to build pipeline for shopping...'
    }

  }
}