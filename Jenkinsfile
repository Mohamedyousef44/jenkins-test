pipeline {
    agent any
    environment{
        DOCKERHUB_CREDENTIALS = credentials('dockerHub')
    }

    stages {
        // stage('GitHub connection'){
        //     steps{
        //         git 'https://github.com/Mohamedyousef44/jenkins-test'   
        //     }
        // }
        stage('DockerHub Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        // stage('build and push'){
        //     steps{
        //         sh 'docker build -t jenkins-test:latest .'
        //         sh 'docker push jenkins-test:latest'
        //     }
        // }
    }
}
