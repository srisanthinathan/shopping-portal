pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'this is the Build job'
        sh 'npm install'
        sleep 4
      }
    }

    stage('Test') {
      steps {
        echo 'this is the Test job'
        sh 'npm test'
        sleep 9
      }
    }

    stage('Package') {
      steps {
        echo 'this is the package job'
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
      echo 'this pipeline has completed...'
    }

  }
}