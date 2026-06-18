pipeline {
    agent any

   
    stages {

        stage('Checkout') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/susmitamathapati/Selenium.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }

        success {
            echo 'Selenium tests executed successfully!'
        }

        failure {
            echo 'Selenium tests failed!'
        }
    }
}
