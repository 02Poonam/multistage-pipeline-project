pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the Java application...'
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                script {
                    echo "Building development branch: ${env.poonam}"
                    withMaven(maven: 'Maven-3.9.0') {
                        sh 'mvn clean package'
                    }
                }
            }
        }
    }
    post {
        success {
            echo 'Build and test succeeded!'
        }
        failure {
            echo 'Build or test failed!'
        }
    }
}
