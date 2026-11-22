pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Downloading employee application from GitHub'
                git 'YOUR_GITHUB_REPOSITORY_URL'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Employee Management Application'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running automated unit tests'
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Creating application JAR'
                sh 'mvn package -DskipTests'
            }
        }

    }

    post {
        success {
            echo 'Employee Application CI Pipeline Successful!'
        }

        failure {
            echo 'Pipeline Failed! Check Console Output.'
        }
    }
}