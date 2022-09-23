pipeline{
    agent any
    stages{
        stage('checkout'){
            steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: 'pipelinetesting']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Manikandan0602/simple-java-maven-app.git']]])

                }
            }

        }
        
    }
}