pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'Localmaven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'Localmaven') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'Localmaven') {
                    sh 'mvn deploy'
                }
            }
        }
        
         stage ('Deployment Validate') {
            steps {
                withMaven(maven : 'Localmaven') {
                    sh 'mvn -v'
                }
            }
        }
    }
}
