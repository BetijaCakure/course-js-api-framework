pipeline {
    agent any
    triggers{
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-api-test-image') {
            steps {
                script{
                    builddockerImage()
                }
            }
        }
    }
    
}

def builddockerImage(){
    echo "Building of node application is starting.."
    sh "docker build -t betija/api-tests ."
    
    echo "Pushing image to docker registry"
    sh "docker push betija/api-tests"
}
