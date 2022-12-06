node ('ubuntu'){  
    def app
    environment {
        dockerhub = credentials('dockerhub')
    }
    stage('Cloning Git') {
        /* Let's make sure we have the repository cloned to our workspace */
      /* checkout scm */
	dir('build') {
          git branch: "release/v8.2.2", url: "https://github.com/WebGoat/WebGoat.git"
      }
    }  
    stage('SAST'){
     /* build 'Sonar-Qube' */   
     }
    stage('Pull-from-dockerhub') {
	sh 'docker pull webgoat/webgoat-8.0'    

    /*  withDockerRegistry([credentialsId: "dockerhub", url: ""]) { */
          /*  app.push("new")*/
        		/*	}*/
         }
    stage('SECURITY-IMAGE-SCANNER'){
        sh 'echo scan image for security'
    }
    stage('Run-image-server') {
    
         sh "docker run -p 9090:9090 -t webgoat/webgoat-8.0"	
      }
    
    stage('DAST')
        {
         sh 'echo dast scan for security'
        }
 
}
