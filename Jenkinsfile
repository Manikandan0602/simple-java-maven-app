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
                    sh 'mvn clean compile'
                }
            }

        }
        stage('test'){
            steps{
                script{
                    echo "maven code test"
                    sh "mvn clean test"
                }
            }
        }
        
    }
}