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
     }

}