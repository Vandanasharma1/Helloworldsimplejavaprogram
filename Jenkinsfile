pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull source code from your repo
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java source...'
                sh '''
                    mkdir -p out
                    javac -d out Helloworld.java
                '''
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                sh '''
                    java -cp out Helloworld
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution finished.'
        }
    }
}
