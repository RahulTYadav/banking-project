pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/RahulTYadav/banking-project.git'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with rahul'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with rahul'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with rahul'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with rahul'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t rahultyadav/bankingproject .'
           }
    }
