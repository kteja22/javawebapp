pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Build') {
            steps {
                withMaven(maven: 'apache-maven-3.6.3'){
                bat 'mvn clean compile'
                }
            }
        }
        stage('Testing') {
            steps {
                withMaven(maven: 'apache-maven-3.6.3'){
                bat 'mvn test'
                }
            }
        }
        stage('package') {
            steps {
                withMaven(maven: 'apache-maven-3.6.3'){
                bat 'mvn clean install'
                }
            }
        }


                                       }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
