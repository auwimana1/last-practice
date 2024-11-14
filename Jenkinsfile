pipeline{
    agent any
    parameters{
        string (name: 'IMAGE', defaultValue: '1.0.0')

    }

    stages{
        stage("build image1"){
            steps{
                script{
                       // This step should not normally be used in your script. Consult the inline help for details.
                    withDockerRegistry(credentialsId: 'ecr:us-east-1:Ade-practice', url: 'https://557195342730.dkr.ecr.us-east-1.amazonaws.com/') {
                    sh "docker build -t niyela:${params.IMAGE} ."
                    sh "docker tag niyela:${params.IMAGE} 557195342730.dkr.ecr.us-east-1.amazonaws.com/original:${params.IMAGE}"
                    sh "docker tag niyela:${params.IMAGE} 557195342730.dkr.ecr.us-east-1.amazonaws.com/original:latest"
                    sh "docker push 557195342730.dkr.ecr.us-east-1.amazonaws.com/original:latest"
                    }
                }
            }
        }
    }
}