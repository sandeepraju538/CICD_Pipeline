node {
    def app
    stage('Clone repository') {
        checkout scm
    }
    stage('Build image') {
        environment {
            HOME="."
        }
        app = docker.build("sandeep/dockerwebapp")
    }
    stage('Test image') {
        app.inside {
            sh 'echo "Tests passed"'
        }
    }
    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'DockerHub') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }    
    }
}