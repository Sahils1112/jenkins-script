@Library("sharedlib") _
pipeline{
    agent any
    
    stages{
        stage("from git"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage('git source'){
            steps{
            script{
            pull("https://github.com/Sahils1112/React_application.git", "master")
        }
        }
        }
        stage('docker compose down'){
            steps{
                echo "shutting the containers"
                sh 'docker-compose down || true'
            }
        }
        stage('docker compose up'){
            steps{
                echo "starting the container"
                sh 'docker-compose up -d --build'
            }
        }
    }
}
