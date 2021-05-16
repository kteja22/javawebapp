pipeline {
    agent any
    tools {
        maven 'apache-maven-3.8.1'
        jdk 'java-11-openjdk-11.0.9.11-0.amzn2.0.1.x86_64'
    }
    stages {
        
        stage ('mclean') {
            steps {
                bat '''
                    cd /Users/ak_mi/IdeaProjects/junitwebapp
                    mvn clean
                    
                    '''

            }
        }
        stage ('mtest') {
            steps {
                bat '''
                     cd /Users/ak_mi/IdeaProjects/junitwebapp
                     mvn test

                 '''

            }
        }

         s
        stage ('mcompile') {
            steps {
                bat '''
                     cd /Users/ak_mi/IdeaProjects/junitwebapp
                     mvn compile

                 '''

            }
        }
        


        stage ('build') {
            steps {
                bat '''
                    cd /Users/ak_mi/IdeaProjects/junitwebapp
                    mvn clean install
                '''

            }
            
        }
        stage ('deployment') {
            steps {
                bat '''
                echo "deploying app from next job"

                 '''

            }
        }
    }
}
