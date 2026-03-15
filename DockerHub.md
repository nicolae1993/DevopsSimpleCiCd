


First step was to set the credential for Jenkins to be able to connect to Dockerhub

![image_alt](https://github.com/nicolae1993/DevopsSimpleCiCd/blob/2a262e6d76fc852f0decd0574e50384dd9bc82a4/images/dockerhub.PNG)

```groovy
   stage("Image Push"){
            steps{
           withCredentials([usernamePassword(credentialsId: 'f9d56717-53ca-4690-a64a-fbfc790386c5', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
            sh 'docker login -u $USER -p $PASS'
            sh "docker image push nicolaestan93/docker_ci:v$BUILD_ID"
            sh "docker image push nicolaestan93/docker_ci:latest"
               }
            }
        }
```

![image_alt](https://github.com/nicolae1993/DevopsSimpleCiCd/blob/ba2852bf7edeca5303356e5fd65b8f8b42fb35cc/images/pushdockerhub.PNG)

![image_alt](https://github.com/nicolae1993/DevopsSimpleCiCd/blob/0ca21a6eb1e40da5610b22d3e018faecab6566be/images/docker_images.PNG)

![image_alt](https://github.com/nicolae1993/DevopsSimpleCiCd/blob/a674cb41857f1108ab2292f06fb2e2771bc1bdbf/images/dockerhubVersion.PNG)
