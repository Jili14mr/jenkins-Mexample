pipeline {
    agent any
    parameters { 
       choice(name: 'ENV', choices: ['DEV', 'UAT', 'PROD'], description: '') }

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : '3.0.5') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : '3.0.5') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : '3.0.5') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
