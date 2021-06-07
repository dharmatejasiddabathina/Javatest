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
                stage('SonarQube analysis') { 
                        environment { 

            //def scannerHome = tool 'SonarScanner 4.10.0'

            MSBUILD_SQ_SCANNER_HOME = tool name: 'sonarscanner', type: 'hudson.plugins.sonar.MsBuildSQRunnerInstallation'

                }

                        steps{
                                script{
         
                  withSonarQubeEnv('My SonarQube Server') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:'Maven 3.5') {
                        bat 'mvn clean package sonar:sonar'
                    }
                                }
                        }
    }
	      }
        }
}
