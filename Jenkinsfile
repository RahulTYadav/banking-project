pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/alekhya167/banking-financeme-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with alekhya'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with alekhya'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with akshat'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with akshat'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t alekhya1607/bankingprojectv1 .'
           }
         }
        stage('Login to dockerhub and push the file'){
            steps{
                with Credentials([string(credentialsId: 'dockerhubpassword', variable: 'dockerhubpass')]) {
                    sh 'docker login -u alekhya1607 -p ${dockerhubpass}'
                    sh ' docker push alekhya1607/bankingprojectv1 '
                }
            }   
        }
    }
}
