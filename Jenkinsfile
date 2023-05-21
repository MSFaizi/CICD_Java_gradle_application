pipeline{
    agent any
    stages{
        stage("Sonarqube quality checks"){
            agent{
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                       sh 'chmod +x gradlew'
                       sh './gradlew sonarqube'
                    }
                }
            }
            
        }
    }
}