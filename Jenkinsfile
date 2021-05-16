pipeline {
    agent any
    tools {
        maven 'apache-maven-3.8.1'
        jdk 'java-11-openjdk-11.0.9.11-0.amzn2.0.1.x86_64'
    }
    stages {

        stage ('mclean') {
            steps {
                sh '''
                    cd /root/javawebapp/junitwebapp
                    mvn clean
                    
                    '''

            }
        }
        stage ('mtest') {
            steps {
                sh '''
                     cd /root/javawebapp/junitwebapp
                     mvn test

                 '''

            }
        }

         s
        stage ('mcompile') {
            steps {
                sh '''
                     cd /root/javawebapp/junitwebapp
                     mvn compile

                 '''

            }
        }
        


        stage ('build') {
            steps {
                sh '''
                    cd /root/javawebapp/junitwebapp
                    mvn clean install
                '''

            }
            
        }
        stage ('deployment') {
            steps {
                sh '''
                echo "deploying app from next job"

                 '''

            }
        }
    }
}
