node {

    checkout scm
    def customImage

    stage('Build image') {
        docker.withRegistry('https://registry.hub.docker.com', 'DockerHub') {
            customImage = docker.build("sandeep/dockerwebapp")
        }
    }
    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'DockerHub') {
            customImage.push()
        }
    }
}