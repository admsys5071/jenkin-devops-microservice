//SCRIPTED

//DECLARATIVE
pipeline {
    agent any
	//agent { docker { image 'node:latest'}}
    stages {
        stage('Build') {
            steps {
				//sh 'mvn --version'
                //sh 'node --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_URL - $env.BUILD_URL"
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

