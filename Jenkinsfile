pipeline{
    agent {
  label 'buildserver'
}

    tools{
        maven 'maven-3'
    }
    stages{
        stage('build'){
            steps{
                script{
                    sh 'mvn clean install'
                }
            }
        }
        stage('unit testing'){
            steps{
                
                    sh 'mvn test'
                }
                post{
                    success{
                        echo "junit testing success, publishing report"
                        junit 'target/surefire-reports/*.xml'
                    }
                    failure{
                        echo "junit testing is failed"
                    }
                }
            }
        stage('sonar'){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'f9e4160f-e4f2-4d60-a350-4d2f4c4eb957') {
                    sh "${tool("my_sonarqube")}/bin/sonar-scanner \
                        -Dsonar.projectKey=simple-java-maven-pipeline \
                        -Dsonar.sources=. \
                        -Dsonar.java.binaries=target \
                        -Dsonar.host.url=http://35.84.134.226:9000 \
                        -Dsonar.login=sqp_f9ab70e415ce53fc0350035e379680183086b89b"
                    }
                }
            }
        }
        stage('upload artifact'){
            steps{
                script{
                    sh 'mvn -s settings.xml deploy'
                }
            }
        }
    }
}

