node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'DockerHub') {
        def customImage = docker.build("sandeep/dockerwebapp")
        /* Push the container to the custom Registry */
       	//  customImage.push()
    }
	docker.withRegistry('https://registry.hub.docker.com', 'DockerHub') {
        docker.push()
	}
}