pipeline{
    agent any
    
    stages{
        stage("Code checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/nicolae1993/DevopsSimpleCiCd.git'
            }
        }
        
           stage("image build"){
            steps{
                sh 'docker image build -t nicolaestan93/docker_ci:v$BUILD_ID /var/lib/jenkins/workspace/ci/getting-started-app-main'
                sh 'docker image tag nicolaestan93/docker_ci:v$BUILD_ID nicolaestan93/docker_ci:latest'
            }
        }
        
        stage("Image Push"){
            steps{
           withCredentials([usernamePassword(credentialsId: 'f9d56717-53ca-4690-a64a-fbfc790386c5', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
            sh 'docker login -u $USER -p $PASS'
            sh "docker image push nicolaestan93/docker_ci:v$BUILD_ID"
            sh "docker image push nicolaestan93/docker_ci:latest"
            sh "docker image rmi nicolaestan93/docker_ci:latest nicolaestan93/docker_ci:v$BUILD_ID"
               }
            }
        }
        
        
         stage("Container creation"){
            steps{
                sh 'docker run -itd --name docker_ci -p 3000:3000 nicolaestan93/docker_ci:latest'
            }
        }
        
        
        
    }
}


