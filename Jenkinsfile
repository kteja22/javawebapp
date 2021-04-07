pipeline {
    agent any
    tools {
        maven 'apache-maven-3.6.3'
        jdk 'jdk1.8.0_281'
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                bat 'cd \Users\ak_mi\IdeaProjects\junitwebapp' 
                bat 'mvn clean'
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}