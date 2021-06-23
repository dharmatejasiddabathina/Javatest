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
            
				
				
      stage ('Deploy') {
    steps{
        sshagent(credentials : ['dockernode-aws']) {
            sh 'ssh -o StrictHostKeyChecking=no ec2-user@18.221.236.246 uptime'
           
           
        }
    }
}
                                          
                                          
   
                          
}
}
