pipeline {
    agent any
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
				mvn install
                                }  

			     }
		                  }
	      }
}
