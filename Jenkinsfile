pipeline {
    agent any
    triggers {
        cron  'H/5 * * * *'
    }
    
    stages{
        stage('checkout') { 
            steps {
                git branch:'main',url:'https://github.com/AnisAY/epsi-dev709-ci.git'
                }
            

        }
        stage('clean') {
        			steps {
			                sh 'chmod u+x ./mvnw'
			                sh './mvnw clean'
			           
			            
            		}	        
        }
        stage('compile') {
			steps {
	                sh 'chmod u+x ./mvnw'
	                sh './mvnw compile'
	            
    		}
    		}
        stage('test') {
			steps {
	                sh 'chmod u+x ./mvnw'
	                sh './mvnw test'
	            
    		}	        
        }
        stage('package') {
    			steps {
		                sh 'chmod u+x ./mvnw'
		  				sh './mvnw package'
		            
        		}
        }	
        stage('archive') {
    			steps {
        			
		            	sh 'mv target/erphrense-0.0.1-SNAPSHOT.jar erphrense-$BUILD_NUMBER.jar'
		  				archiveArtifacts artifacts: 'erphrense-*.jar', followSymlinks: false

        		}        
 		}

        }
    }

