pipeline {
  agent {
    docker {
      image 'node:16-alpine'
      args '--user root -v /var/run/docker.sock:/var/run/docker.sock' // mount Docker socket to access the host's Docker daemon
    }
  }
  stages {
    stage('Build and Test') {
      steps {
        sh 'ls -ltr'
        // build the project and create a JAR file
        sh 'cd server && npm i'
        sh 'cd ..'
        sh 'cd client && npm i'
      }
    }
  }
}
