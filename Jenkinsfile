pipeline{
    agent any
    tools{
        maven 'maven-3'
    }
    stages{
        stage("build"){
            steps{
                script{
                 sh 'mvn install'
                }
            }
            
        }
        stage("test"){
          steps{
            script{
                sh 'mvn test'
            }
          }  
        }
        stage("sonar"){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'my sonar') {
                        sh "${tool("my sonar")}/bin/sonar-scanner \
                        -Dsonar.projectKey=simple-java-maven-app \
                        -Dsonar.sources=. \
                        -Dsonar.java.binaries=target \
                        -Dsonar.host.url=http://44.242.136.164:9000 \
                        -Dsonar.login=sqp_d6b135da71b1534c41cc60766f8e7294ab9abcca"
                }
            }
        }
        stage("upload artifact"){
            steps{
                script{
                    sh 'mvn -s setting.xml deploy'
                }
            }
        }
        
    }
}