pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git branch: 'main',
                    credentialsId: 'github-creds',
                    url: 'https://github.com/baludinakar2000-cmyk/sample-webapp.git'
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    rsync -avz ./ ec2-user@3.110.107.96:/var/www/html/
                '''
            }
        }
    }
}
