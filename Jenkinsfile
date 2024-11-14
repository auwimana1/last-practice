pipeline{
    agent any
    parameters{
        string (name: 'IMAGE', defaultValue: '1.0.0')

    }

    stages{
        stage("build image1"){
            steps{
                script{
                    sh "docker build -t niyela:${params.IMAGE} ."
                    sh "docker tag niyela:${params.IMAGE} 557195342730.dkr.ecr.us-east-1.amazonaws.com/original:${params.IMAGE}"
                    sh "docker tag niyela:${params.IMAGE} 557195342730.dkr.ecr.us-east-1.amazonaws.com/original:latest"
                    sh "docker push 557195342730.dkr.ecr.us-east-1.amazonaws.com/original:latest"

                }
            }
        }
    }
}