pipeline{
    agent any
    tools{
        maven 'maven-2'
    }
    stages{
        stage('build'){
            steps{
                script{
                    echo "maven code build"
                    sh 'mvn clean install'
                }
            }

        }
        
        
    }
}