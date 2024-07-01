node {
    def app
    stage('Clone repository') {
      checkout scm
    }

    stage('Build image') {
      app = docker.build("delhombre/j3-webdev")
    }

    stage('Push image to Docker Hub') {
      docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-credentials') {
        app.push("latest")
      }
    }
}