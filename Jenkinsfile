pipeline {
    agent any
       /* envirnoment{
             // path = 'D:\apache-maven-3.8.1:$path'
                   }*/
	stages{
		stage('checkout'){
			steps {
				deleteDir()
				checkout scm

			     }
		                  }
                stage('Build'){
			steps {
                                script{
                                     bat '''
                                     
                                        set M2_HOME="D:/apache-maven-3.8.1"
                                        set path="D:/apache-maven-3.8.1/bin";%path%
				        
                                        mvn clean install
                                        
                                        '''
                                }  

			     }
		                  }
               /* stage('SonarQube analysis') { 
                       

                        steps{
                                script{
                        
                  withSonarQubeEnv('sonar') {
                                        
                    // Optionally use a Maven environment you've configured already
					
                    withMaven(maven:'maven-3.8.1'){
					    
						
                            
                             
                             bat 'mvn clean package sonar:sonar'
                            
							
                    }
                                }
                        }
    }
	      }
		  
		  stage("Quality Gate"){
                          steps {
                           sleep(10)
              timeout(time: 1, unit: 'HOURS') {
                waitForQualityGate abortPipeline: true
                        
              }
							}
		
		  
        } */
		
		stage("nexus upload"){
                        steps{      
		script{
		nexusArtifactUploader credentialsId: 'nexus-cred', groupId: 'com.test', nexusUrl: 'http://localhost:8081/', nexusVersion: 'nexus3', protocol: 'http', repository: 'javatest-nexus', version: '0.0.1-snapshot'
		}
                        }
		
		}
}
}
