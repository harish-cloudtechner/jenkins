pipeline {
	    agent any
	    tools {
	        maven 'maven'   
	        }
	    stages {
	        stage ('Git Checkout') {
	            steps {
	                git branch: 'main',
			credentialsId: '74b74552-0563-49e5-9d85-b9bbccaedff2',
			url: 'https://github.com/harish-cloudtechner/jenkins.git'
	                }
	            } 
		stage ('Compile') {
	            steps {
	                sh 'mvn compile'
	                }
	            }      
	        stage ('Package') {
	            steps {
	                sh 'mvn package'
	                }
	            }
	        stage ('Install') {
	            steps {
	                sh 'mvn install'
	                }
	            }
		    
		 stage ('Create war file') {
	            steps {
	                sh 'jar -cf target/dependency/webapp-runner.jar target/*.war'
	                }
	            }
		    
                stage ('Deploy War File') {
                        steps {
                                sh "cp target/*.war /home/harish/apache-tomcat-8.5.69/webapps"
                        }
                }
	}
}
