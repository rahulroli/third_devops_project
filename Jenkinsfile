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
                    sh 'docker build -t third-devops-project:latest .'
                 
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'docker run -d -p 9080:80 third-devops-project:latest'
                }
            }
        }
    }
}
