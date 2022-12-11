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
	sh 'docker pull webgoat/goatandwolf'    

    /*  withDockerRegistry([credentialsId: "dockerhub", url: ""]) { */
          /*  app.push("new")*/
        		/*	}*/
         }
    stage('Post-to-dockerhub'){
	sh "docker tag webgoat/goatandwolf:latest peggyvr/webgoat-devsecops:new"
	app = docker.image('peggyvr/webgoat-devsecops:new')
	withDockerRegistry([credentialsId: "dockerhub", url: ""]) {  
	  app.push("new")              
         }
    }
    stage('SECURITY-IMAGE-SCANNER'){
        sh 'echo scan image for security'
    }
    stage('Run-image-server') {
    
        sh "docker run --detouch -p 8080:8080 -p 9090:9090 -p 80:8888 -e TZ=Europe/Athens peggyvr/webgoat-devsecops:new" 	
      }
    
    stage('DAST')
        {
         sh 'echo dast scan for security'
        }
 
}
