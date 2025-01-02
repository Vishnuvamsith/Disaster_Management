pipeline {
  agent {
    docker {
      image 'node:23-alpine'
      args '--user root'// mount Docker socket to access the host's Docker daemon
    }
  }
  stages {
    stage('Build and Test(backend)') {
      steps {
        sh 'ls -ltr'
        // build the project and create a JAR file
        sh 'cd server && rm -rf node_modules'
        sh 'cd server && npm install'
      }
    }
    stage('Build and Test(frontend)') {
      steps {
        sh 'ls -ltr'
        // build the project and create a JAR file
        sh 'cd client && npm cache clean --force && CI=true npm install --verbose'
      }
    }
  }
}
