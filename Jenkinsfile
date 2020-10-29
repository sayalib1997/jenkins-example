pipeline {
    agent any
     tools {
        maven 'maven_3_5_0' 
    }

    stages {
        stage ('Compile Stage') {

            steps {
                
                      bat "mvn clean compile" 
                
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
