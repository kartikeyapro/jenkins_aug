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
				-Dsonar.host.url=http://192.168.29.27:9000 \
				-Dsonar.login=c0aa3ef0ce8ffd607bab400cd752390363776c28'
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

