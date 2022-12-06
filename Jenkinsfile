node ('ubuntu'){  
    def app
    environment {
        dockerhub = credentials('dockerhub')
    }
    stage('Cloning Git') {
        /* Let's make sure we have the repository cloned to our workspace */
       steps{
	 git branch: 'develop', url: 'https://github.com/WebGoat/WebGoat.git'
	}
    }  
    stage('SAST'){
     /* build 'Sonar-Qube' */   
     }

    
    stage('Build-and-Tag') {
    /* This builds the actual image; synonymous to
         * docker build on the command line 
        app = docker.build("peggyvr/snake:new")*/
    }
    stage('Post-to-dockerhub') {
    
     /*withDockerRegistry([credentialsId: "dockerhub", url: ""]) {
            app.push("new") */
        			}
         }
    stage('SECURITY-IMAGE-SCANNER'){
        sh 'echo scan image for security'
    }
  
    
    stage('Pull-image-server') {
    
       /*  sh "docker-compose down"
         sh "docker-compose up -d" */	
      }
    
    stage('DAST')
        {
         sh 'echo dast scan for security'
        }
 
}
