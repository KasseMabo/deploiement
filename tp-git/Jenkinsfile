pipeline {
    agent {label 'docker'}

    stages{
        stage('Docker Build Image'){
            steps{
                script{
                    sh 'docker build -t kasse:v1 .'
                }
            }

        }

        stage('Docker tag image') {
            steps {
                script {
                    sh 'docker tag kasse:v1 abdoukasse/kasse:v1'
                    sh 'docker images'
                }
            }
        }

        stage('Docker push image') {
            steps {
                script {
                    sh 'docker push abdoukasse/kasse:v1'
                }
            }
        }
    }

    // environment {
    //     DOCKER_PASSWORD=credentials('DOCKER_PASSWORD')
    // }

    // stages {
    //     stage('Docker login') {
    //         steps {
    //             script {
    //                 sh 'echo $DOCKER_PASSWORD | docker login -u abdoukasse --password-stdin'
    //             }
    //         }
    //     }

        // stage('Docker build image') {
        //     steps {
        //         script {
        //             sh 'docker build -t uadb:v1 .'
        //         }
        //     }
        // }

        

        
}