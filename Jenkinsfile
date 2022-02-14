pipeline{
    agent any
    stages{
        stage('Git clone'){
            steps{
                git 'https://github.com/shazforiot/HelloWorld-Springboot-App.git'
            }
        }
        
        stage('maven build'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Create Dockerimage'){
            steps{
                sh 'docker build -t pruebadocker/pipeline:latest .'
            }
        }
 	stage('Create Container'){
            steps{
                sh 'docker run -d pruebadocker/pipeline:latest'
            }
        }
        
    }
}
