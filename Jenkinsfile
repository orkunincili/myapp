String gitUrl = "https://github.com/orkunincili/myapp.git"
pipeline {
  agent any
  stages{
                stage("Git Clone the Source Code"){
                    steps{
                        sh """
		    
                        git clone $gitUrl
		            
                        """
                    }
                }
                
                
                stage("Build Dockerfile"){
                    steps{
                        sh """
		                cd ./myapp
                        docker build  -t myappimage .
		            
                         """
                    }
                }
                
                stage("Tag Image"){
                    steps{
                        sh """
    		    
                        docker image tag myappimage 10.48.6.174:5000/myappimage
    		            
                        """
                    }
                }
                
                stage("Push Docker Image"){
                    steps{
                        sh """
                        docker push 10.48.6.174:5000/myappimage
                        """
                    }
                }
  }
}
