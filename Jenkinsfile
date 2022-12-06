pipeline{
    agent any
    tools{
        maven 'maven-3'
    }
    stages{
        stage('build'){
            steps{
                script{
                    echo "maven code build"
                    sh 'mvn clean intall'
                }
            }
        }
        
    }
}