pipeline {
    agent any    
    environment {
        K8S_HOST_IP = credentials('K8s-Host-IP') //username and ip
        DEPLOYMENT_FILENAME = 'Deploy-webtools-trace-private.yaml'
    }
    stages {
        stage('Git Stuff') {
            steps {
                script {
                	checkout scmGit(
                		branches: [[name: '*/master']], 
                		extensions: [], 
                		userRemoteConfigs: [[url: 'https://github.com/ikoyski/webtools-trace.git']]
                	)
                }
            }
        }        
        stage('K8s Stuff') {
        	steps {        		
        		script {
        			sshagent(['K8s-Host-User-With-Key']) {
					sh 'scp -o StrictHostKeyChecking=no $DEPLOYMENT_FILENAME $K8S_HOST_IP_USR@$K8S_HOST_IP_PSW:/home/ikoyski'
					sh 'ssh -o StrictHostKeyChecking=no $K8S_HOST_IP_USR@$K8S_HOST_IP_PSW kubectl apply -f $DEPLOYMENT_FILENAME'
		        	}
			}
        	}
        }
    }
}
