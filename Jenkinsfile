pipeline{
    agent any
    options{
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    environment{
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }
    stages{
        stage('Build'){
            steps{
                sh 'docker build -t kushaggarwal/nodejs-webapp .'
            }
        }
        stage('Test'){
            steps{
                echo "This is a test stage"
            }
        }
        stage('Deploy'){
            steps{
                echo "This is a deploy stage"
            }
        }
        stage('Monitor'){
            steps{
                echo "This is a monitor stage"
            }
        }
    }
}