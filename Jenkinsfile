node{
     
    stage('SCM Checkout'){
        git credentialsId: 'GIT_CREDENTIALSS', url: 'https://github.com/manikarnam/node-hello.git', branch: 'master'
    }
    
    stage('Build Docker Image'){
	    bat "docker build -t maniengg/hello-world:latest"
    }
    stage('Push Docker Image'){
        withCredentials([string(credentialsId: 'DOKCER_HUB_PASSWORD', variable: 'DOKCER_HUB_PASSWORD')]) {
          bat "docker login -u maniengg -p ${DOKCER_HUB_PASSWORD}"
        }
        bat "docker push maniengg/php-redis:latest"
      }
    }
