pipeline{
    agent { label 'node1' }
    tools {
        maven 'maven3.9'
        jdk  'java17'
    }
    stages{
        stage('git checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/tarik0621/spring-petclinic.git'
            }
        }
        stage('build stage'){
            steps{
               sh 'mvn clean package'
            }
        }
         stage("SonarQube analysis") {
          node {
              withSonarQubeEnv('sonar-server', credentialsId: 'sonarid') {
                 sh 'mvn sonar:sonar'
              }
          }
      }
    }
}

