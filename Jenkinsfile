node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("ddujji / flask-example")
         
     }
     stage('Push image') {
         #docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
         docker.withRegistry('https://hub.docker.com/u/peanutbutterrrrrr', 'docker-hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}

stage('Build image') {
  app = docker.build("ddujji / flask-example")
}

stage('Push image') {
  #docker.withRegistry('https://registry.hub.docker.com', 'docker-hub')
  docker.withRegistry('https://hub.docker.com/u/peanutbutterrrrrr', 'docker-hub') 
  {
     app.push("${env.BUILD_NUMBER}")
     app.push("latest")
  }
}

