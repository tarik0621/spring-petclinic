pipeline{
    agent { label 'node1' }
    tools {
        maven 'maven3.9'
        jdk  'java17'
    }
    stages{
    //     stage('git checkout'){
    //         steps{
    //             git branch: 'main', url: 'https://github.com/tarik0621/spring-petclinic.git'
    //         }
    //     }
    //     stage('build stage'){
    //         steps{
    //            sh 'mvn clean package'
    //         }
    //     }
    //      stage("SonarQube analysis") {
    //       steps {
    //           withSonarQubeEnv(installationName: 'sonar-server', credentialsId: 'sonarid') {
    //              sh 'mvn sonar:sonar'
    //           }
    //       }
    //   }
       stage('docker build stage'){
            steps{
             sh '''
                   sudo docker build -t tarikahmad0621539/springpetclinic:1.1 .
                   sudo docker run -d --name spc -p 8080:8080 tarikahmad0621539/springpetclinic:1.1
                '''
            }
        }
    }
}

