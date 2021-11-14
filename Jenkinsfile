node {

    stage('SCM Checkout') {
		git credentialsId: '2814d10c-b312-48b6-a032-54829a2de338', url: 'https://github.com/sandeepraju538/CICD_Pipeline'
    }

	stage("Build Docker Image") {
		sh "docker build - < Dockerfile"
	}

	stage('Upload Image to DockerHub') {
        withCredentials([string(credentialsId: 'DockerHub', variable: 'DockerHub')]) {
			sh "docker login -u sandeepraju538 -p ${DockerHub}"
        }
        sh 'docker push sandeep/dockerwebapp:1.0.0'
  	}

	stage("Running Docker Image") {
		sh "docker run --name dockerwebapp dockerwebapp"
	}
}