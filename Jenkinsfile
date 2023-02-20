pipeline {
    agent any
    environment {
        dockerhub=credentials('dockerhub')
    }
    stages {
        stage('git_checckout') {
            steps {
                git branch: 'main', url: 'https://github.com/lijitijil/Project.git
'
            }
        }
        stage('Docker_build') {
            steps {
                sh 'sudo docker build -t htmlpage .'
            }
        }
        stage('Dockerimages') {
            steps {
                sh 'sudo docker images'
            }
        }
        stage('Docker_push') {
            steps {
                sh 'sudo docker tag htmlpage lijitijil/htmlpage'
                sh 'docker login -u $dockerhub_USR -p $dockerhub_PSW'
                sh 'sudo docker push lijitijil/htmlpage'
            }
        }
    }
}
