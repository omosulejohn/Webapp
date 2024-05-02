pipeline{
    agent any 
    options{
        buildDiscarder(logRotator(numToKeepStr:'5'))
    }
    environment{
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }
    stages{
        stage('Build docker image'){
            steps{
                echo "Building the docker image from Dockerfile in src directory"
                sh 'docker build -t kushaggarwal/web-project .'
            }
        }
        stage('Login into the dockerhub account'){
            steps{
                echo "Logging into dockerhub account for pushing the image"
                sh "echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin"
            }

        }
        stage('Push docker image on dockerhub online'){
            steps{
                echo "Execute the pushing command for image onto dockerhub"
                sh "docker push kushaggarwal/web-project"
            }
        }

    }
}
