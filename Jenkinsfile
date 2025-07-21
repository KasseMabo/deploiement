pipeline {
    agent {label 'docker'}

    stages{
        stage('Docker Build Image'){
            steps{
                script{
                    sh 'docker build -t kasse:v2 .'
                }
            }

        }

        stage('Docker tag image') {
            steps {
                script {
                    sh 'docker tag kasse:v2 abdoukasse/kasse:v2'
                    sh 'docker images'
                }
            }
        }

        stage('Docker push image') {
            steps {
                script {
                    sh 'docker push abdoukasse/kasse:v2'
                }
            }
        }

        stage('Deploiement du service') {
            steps {
                script {
                    sh 'kubectl apply -f manifests/service.yaml'
                }
            }
        }

        stage('Deploiement de l\'application') {
            steps {
                script {
                    sh 'kubectl apply -f manifests/deployment.yaml'
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