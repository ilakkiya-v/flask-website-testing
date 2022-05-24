pipeline {
	agent any
	    stages {
	        stage('Clone Repository') {
	        /* Cloning the repository to our workspace */
	        steps {
	        checkout scm
	        }
	   }
	   stage('Build Image') {
	        steps {
	        bat 'docker build -t flask_web_dev:v1 .'
	        }
	   }
	   stage('Run Image') {
	        steps {
	        bat 'docker run -d -p 5000:5000 --name flask_web flask_web_dev:v1'
	        }
	   }
	   stage('test PythonEnv') {
			steps {
					bat 'python -m pytest' 
			}
	   }
		}
}