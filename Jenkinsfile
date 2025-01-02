pipeline {
  agent {
    docker {
      image 'node:16-alpine'
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
        sh 'cd server && npm start'
      }
    }
    stage('Build and Test(frontend)') {
      steps {
        sh 'ls -ltr'
        // build the project and create a JAR file
        sh 'cd client && npm i'
        sh 'cd client && npm start'
      }
    }
  }
}
