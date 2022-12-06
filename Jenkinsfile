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
        stage('test'){
            steps{
                script{
                    echo "maven code test"
                    sh 'mvn test'
                }
            }
        }
        stage('install'){
            steps{
                script{
                    echo "maven code install"
                    sh 'mvn install'
                }
            }
        }
    }
}