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
        
       stage('Login to Docker Hub') {
    steps {
        withCredentials([string(credentialsId: 'dockerhub_cred', variable: 'samindocker')]) {
            script {
                bat "docker login -u rahuldubey1993 -p %samindocker%"
            }
        }
    }
}

stage('Push Image') {
    steps {
        bat 'docker push rahuldubey1993/rahul_docker_reop:%BUILD_NUMBER%'
    }
}
        
        
    }
}
