pipeline{
    agent any

    stages{
        stage ("CONTINOUS DOWNLOAD"){
            steps{
                git branch: 'main', url: 'https://github.com/ZinebSG/LAWFIRM.git'
            }
        }
        stage("UNIT TEST"){
            steps{
                sh'mvn test'
            }
        }
        stage("INTEGRATION TEST"){
            steps{
                sh'mvn verify -DskipUnitTests'
                
            }
        }
        stage("CONTINOUS BUILD"){
            steps{
                sh'mvn clean install'
                
            }
        }
        stage("STATIC Test Analyxis"){
            steps{
                script {
                    withSonarQubeEnv(credentialsId: 'Sonar-token') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
        stage("Continous Delivery"){
            steps{
                script {
                    
                        sh 'cp -r /home/ubuntu/.jenkins/workspace/Pipline-zineb/ /var/www/html/'
                        
                    
                }
            }
        }
    }
}