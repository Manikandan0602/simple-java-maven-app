pipeline{
    agent any
    tools{
        maven 'maven-3'
    }
    stages{
        stage('compile'){
            steps{
                script{
                    echo "maven compile"
                    sh 'mvn clean compile'
                }
            }
        }
        stage('test'){
            steps{
                script{
                    echo "maven test"
                    sh 'mvn clean test'
                }
            }
        }
    }
}