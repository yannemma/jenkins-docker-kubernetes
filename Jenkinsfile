pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("my-yann:latest", ".")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    def customImage = docker.image("my-yann:latest")
                    customImage.run("-p 8086:8080")
                }
            }
        }
    }
}
