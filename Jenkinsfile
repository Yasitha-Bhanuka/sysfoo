pipeline {
    agent any

    tools{
        maven 'Maven 3.9.6'
    }

    stages{
        stage('build'){
            steps{
                echo 'Compiling sysfoo application.....'
                sh 'mvn compile'
            }
        }
        stage('test'){
            steps{
                echo 'Running unit tests.....'
                sh 'mvn clean test'
            }
        }
        stage('package'){
            steps{
                echo 'Packaging the application........'
                sh 'mvn package -DskipTests'
            }
        }
    }

    post {
        always{
            echo 'This pipeline executed completed.'
        }
    }
}
