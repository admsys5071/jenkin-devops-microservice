//SCRIPTED

//DECLARATIVE
pipeline {
    agent any
	//agent { docker { image 'node:latest'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
    tools {
        maven 'myMaven'
        jdk 'jdk11'
    }
    stages {
        stage('Checkout') {
            steps {
				sh 'mvn --version'
                sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_URL - $env.BUILD_URL"
            }
        }
        stage('Compile'){
            steps{
                sh "mvn clean compile"
            }
        }
        stage('Test') {
            steps {
                sh "mvn test"
            }
        }

        stage('Integration test') {
            steps {
                sh "mvn failsafe:integration - test failsafe:verify"
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

