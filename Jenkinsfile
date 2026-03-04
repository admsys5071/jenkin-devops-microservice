//SCRIPTED

//DECLARATIVE
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build"
            }
        }

        stage('Test') {
            steps {
                echo "Test"
            }
        }

        stage('Integration Test') {
            steps {
                echo "Integration Test"
            }
        }
    } // Fin du bloc stages

    post {
        always {
            // Utilisation de doubles quotes pour gérer l'apostrophe de "I'm"
            echo "I'm awesome; I run always"
        }
        success {
            echo 'I run when you are successful'
        }
        failure {
            echo 'I run when you fail'
        }
    } // Fin du bloc post
} // Fin de la pipeline

