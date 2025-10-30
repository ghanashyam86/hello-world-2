pipeline{
     agent any
	   
	  tools {
	     maven 'maven'
		 }
		
     stages{
	   stage('clone git repo'){
	      steps{
		     dir('/mnt/'){
			   
			    sh 'sudo rm -rf /mnt/hello-world-2'
				sh 'git clone https://github.com/ghanashyam86/hello-world-2.git'
				}
			}
		}
		
		stage('build project'){
		    steps{
		        dir('/mnt/hello-world-2'){
		            sh 'mvn clean install -DskipTests'
		        }
		    }
		}
		stage('build docker imgae'){
		    steps{
		        dir('/mnt/hello-world-2'){
		            sh 'docker build -t cloths .'
		        }
		    }
		}
		stage('create docker container'){
		    steps{
		       // sh 'docker stop new'
		       // sh 'docker rm new'
		        sh 'docker run -itd -p 8082:8080 --name cloths-container cloths'
		    }
		}
     }
}
		
		
