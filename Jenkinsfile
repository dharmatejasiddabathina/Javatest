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
		
		/*stage("nexus upload"){
                        steps{      
		script{
                        nexusArtifactUploader artifacts: [[artifactId: 'spring-boot-starter-parent', classifier: '', file: 'target/spring-petclinic-2.4.5.jar', type: 'jar']], credentialsId: 'nexus-cred', groupId: 'org.springframework.boot', nexusUrl: 'localhost:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'javatest-nexus', version: '2.4.5'
                       
		/*nexusArtifactUploader credentialsId: 'nexus-cred', groupId: 'com.test', nexusUrl: 'http://localhost:8081/', nexusVersion: 'nexus3', protocol: 'http', repository: 'javatest-nexus', version: '0.0.1-snapshot'
		*/
                        
                }
                        }
		
		}*/
                /*stage("nexus download")
                {
                        steps {
				println "Downloading from nexus repo..."
                script{
                  bat  'curl --user admin:Dharma@481 -o spring-petclinic-2.4.5.jar http://localhost:8081/javatest-nexus/spring-petclinic-2.4.5.jar'
                            
                        /*
                    downloadNexusArtifact groupId: 'org.springframework.boot',
                    artifactId: 'spring-boot-starter-parent',
                    repo:'javatest-nexus',
                    release: ''.toBoolean(),
                    extension: 'jar',
                    version: '2.4.5',
                    downloadFileName: 'spring-petclinic-2.4.5.jar' */
					
                    
                }
				}
                }*/
				
				stage('remote-aws'){
				
				steps{
                                        script{
				  sshagent(['dockernode-aws']) {
				  
				   sh 'ls -lart'
   
                          }
                                        }
				}
				
				}
}
}
