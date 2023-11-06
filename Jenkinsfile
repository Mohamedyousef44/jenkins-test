pipeline {
    agent any
    environment{
        DOCKERHUB_CREDENTIALS = credentials('dockerHub')
    }

    stages {
        // stage('Checkout') {
        //     steps {
        //         script {
        //             checkout scm
        //             // Access the commit ID
        //             def commitId = currentBuild.changeSets[0].revisions[0].SHA1
        //             sh ' echo Commit ID: ${commitId}'
        //         }
        //     }
        // }
        stage('DockerHub Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('build and push'){
            steps{
                sh 'docker build -t jenkins-test:latest .'
                sh 'docker push jenkins-test:latest'
            }
        }
    }
}
