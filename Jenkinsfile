pipeline {
    agent any
    environment{
        DOCKERHUB_CREDENTIALS = credentials('dockerHub')
    }

    stages {

        stage('build image'){
            steps{
                sh 'docker build -t jenkins-test:latest .'
                sh 'docker images'
                
            }
        }
        stage('push to dockerhub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                sh 'docker push $DOCKERHUB_CREDENTIALS_USR/jenkins-test:latest'
            }
        }
    }
}
