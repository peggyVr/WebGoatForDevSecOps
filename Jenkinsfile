node ('ubuntu'){  
    def app
    environment {
        dockerhub = credentials('dockerhub')
    }
    stage('Cloning Git') {
        /* Let's make sure we have the repository cloned to our workspace */
	 git clone "ssh://git@github.com:WebGoat/WebGoat.git"
    }  
    stage('SAST'){
     /* build 'Sonar-Qube' */   
     }
    stage('DAST')
        {
         sh 'echo dast scan for security'
        }
 
}
