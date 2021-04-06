pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage ('Build') {

                    git url: 'https://github.com/kteja22/javawebapp.git'

                    withMaven(
                    // Maven installation declared in the Jenkins "Global Tool Configuration"
                    maven: 'apache-maven-3.6.3', // (1)
                    // Use `$WORKSPACE/.repository` for local repository folder to avoid shared repositories
                    //mavenLocalRepo: '.repository', // (2)
                   // Maven settings.xml file defined with the Jenkins Config File Provider Plugin
                   // We recommend to define Maven settings.xml globally at the folder level using
                   // navigating to the folder configuration in the section "Pipeline Maven Configuration / Override global Maven configuration"
                   // or globally to the entire master navigating to  "Manage Jenkins / Global Tools Configuration"
                  // mavenSettingsConfig: 'my-maven-settings' // (3)
                     ) {

                   // Run the maven build
                   bat "cd \Users\ak_mi\IdeaProjects\junitwebapp"
                
                   bat "mvn clean verify"

                   } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe & FindBugs & SpotBugs reports...
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