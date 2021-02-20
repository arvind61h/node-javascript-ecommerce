pipeline{
    agent {label 'buildServer'}
    stages{
        stage('scm-checkout'){
        
            steps{
                git 'https://github.com/arvind61h/node-javascript-ecommerce.git'
            }
        }
        stage("Build-Image"){
            steps{
                sh 'docker build -t 92840/front:v${BUILD_NUMBER} -f Dockerfile.frontend .'
                sh 'docker build -t 92840/back:v${BUILD_NUMBER} -f Dockerfile.backend .'
            }
        }
        stage("deployingToRepository"){
            steps{

                sh 'docker push 92840/front:v${BUILD_NUMBER}'
                sh 'docker push 92840/back:v${BUILD_NUMBER}'
            }
        }

    }
}