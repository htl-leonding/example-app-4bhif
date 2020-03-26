node {
    def app

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build('htl-leonding/example-app-4bhif')
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com',
                            'docker-hub-credentials2') {
            app.push('latest')
        }
    }
}

