pipeline {

	    agent any

	    tools {

	        maven 'maven'

	        }

	    stages {

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
		    stage ('create War File') {

                        steps {

                                sh "jar -cf target/dependency/webapp-runner.jar target/*.war"

                        }

                }


                stage ('Deploy War File') {

                        steps {

                                sh "cp target/*.war /root/apache-tomcat-8.5.61/webapps/"

                        }

                }

	}

}
