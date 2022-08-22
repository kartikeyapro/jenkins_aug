pipeline {
    agent any
	tools {
	maven 'Maven 3.0.5'
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
		stage('SonarQube Scan'){
			steps {
			sh 'mvn sonar:sonar \
				-Dsonar.host.url=http://34.173.229.117:9000 \
				-Dsonar.login=c3af2ee2211a0544d0821b6008788b72a5241913'
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

