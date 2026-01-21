pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/rahulroli/third_devops_project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("third-devops-project:latest")
                 
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    docker.image("third-devops-project:latest").run("-p 9080:80")
                }
            }
        }
    }
}
