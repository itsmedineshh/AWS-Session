pipeline {
    agent any
    stages{
        stage('Git checkout'){
            steps{
                git branch: 'master', url: 'https://github.com/itsmedineshh/AWS-Session.git'
            }
        }
        stage('Build image'){
            steps{
                sh 'docker build -t node_image .'
            }
        }
        stage('Docker old container remove'){
            steps{
                sh 'docker rm -f node_container || true'
            }
        }
        stage('run container'){
            steps{
                sh 'docker run -d -p 3000:3000 --name node_container node_image'
            }
        }
    }
}
