pipeline {
    agent any
        envirnoment{
              path = 'D:\apache-maven-3.8.1:$path'
                   }
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
				sh 'mvn clean install'
                                }  

			     }
		                  }
	      }
}
