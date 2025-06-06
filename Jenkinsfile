pipeline {
    agent any
    triggers{
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-api-tests-image') {
            steps {
                buildDockerImage()
            }
        }
    }
}

def buildDockerImage(){
    echo "Building of node application is starting.."
    sh "docker build -t aceskaemilija/api-tests:lates ."

    echo "Pushing image to docker registry.."
    sh "docker push aceskaemilija/api-tests"
}