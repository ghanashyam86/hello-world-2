@Library('my-shared-library') _

pipeline{
     agent any
	   
	  tools {
	     maven 'maven'
		 }
		
     stages{
	   stage('clone git repo'){
	      steps{
				gitClone("https://github.com/ghanashyam86/hello-world-2.git")	
			}
		}
		
		stage('build project'){
		    steps{
		            mavenBuild('/mnt/hello-world-2')    
		    }
		}
		stage('build docker imgae'){
		    steps{
		            dockerBuild('/mnt/hello-world-2', "newimage")
		            
		    }
		}
		stage('create docker container'){
		    steps{
		        dockerRun("mynew-container", "newimage", "8080:8080"
		    
		    }
		}
     }
}
		
		
