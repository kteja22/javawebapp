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

         stage ('msonar') {
            steps {
                bat '''
                     cd /Users/ak_mi/IdeaProjects/junitwebapp
                     mvn clean verify sonar:sonar -Dsonar.login=1d118aa06502adca014746d2938226b6f18492d4

                 '''

            }
        }
        stage ('mcompile') {
            steps {
                bat '''
                     cd /Users/ak_mi/IdeaProjects/junitwebapp
                     mvn compile

                 '''

            }
        }
        stage ('mowasp') {
            steps {
                bat '''
                     cd C:/Program Files/OWASP/Zed Attack Proxy
                     zap.sh -daemon -quickurl http://localhost:8080/ -quickout /tmp/myresults.xml -quickprogress

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
                cd /Program Files/Apache Software Foundation/Tomcat 9.0/webapps
                COPY C:/Users/ak_mi/IdeaProjects/junitwebapp/target/junitwebapp.war
        
                
                '''

            }
        }
    }
}
