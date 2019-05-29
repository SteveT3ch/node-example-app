node {
    def app

    stage('Clone repo'){
        checkout scm
    }

    stage('Build Image'){
        app = docker.build('stevet3ch/node-example-app')
    }

    stage('Push image'){
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credential'){
            app.push(latest)
        }
    }
}