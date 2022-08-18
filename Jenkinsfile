pipeline {
    agent any
	tools {
	maven 'Maven 3.8.6'
        }

    stages {
        stage('Clone') {
            steps {
               git credentialsId: 'git', url: 'https://github.com/kartikeyapro/ks.git'
            }
			}
		stage('Maven Version') {
            steps {
               sh 'mvn --version'
            }
			}	
		stage('Clean') {
            steps {
              sh 'mvn clean' 
            }
			}
	    stage('validate') {
            steps {
            sh 'mvn validate'   
            }
			}
		stage('compile') {
            steps {
            sh 'mvn compile'   
            }
			}
        stage('package') {
            steps {
            sh 'mvn package'   
            }
        }
        stage('Deploy'){
            steps {
            sh 'mvn deploy'     
            }
            }
            
        }
   }

