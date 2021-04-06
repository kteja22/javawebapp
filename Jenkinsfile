pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withMaven(maven: 'apache-maven-3.6.3'){
                bat 'mvn clean compile'
                }
            }
        }
        stage('Test') {
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
            }
<<<<<<< HEAD:Jenkinsfile.txt
=======
        }
    }

>>>>>>> ee079c7f635fcec386035cb645d7ad2d34e34b75:Jenkinsfile
