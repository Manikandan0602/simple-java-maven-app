pipeline{
    agent any
    tools{
        maven 'maven-3'
    }
    stages{
        stage('compile'){
            steps{
                script{
                    echo "maven code compile"
                    sh 'mvn compile'
                }
            }
        }
    }
}