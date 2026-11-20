
pipeline {
    agent any


    stages {

        stage('Git') {
            steps {
                git branch: 'main',
                url: 'https://github.com/pranathi-13/E-ticketing.git'
            }
        }
        
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.war', fingerprint: true
        }

        failure {
            echo 'Build Failed'
        }
    }
}
