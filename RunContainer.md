
```groovy
    stage("Container creation"){
            steps{
                sh 'docker run -itd --name docker_ci -p 3000:3000 nicolaestan93/docker_ci:latest'
            }
        }

```

```
 docker ps
CONTAINER ID   IMAGE                            COMMAND                  CREATED         STATUS         PORTS                                         NAMES
bb5c65668855   nicolaestan93/docker_ci:latest   "docker-entrypoint.s…"   8 seconds ago   Up 8 seconds   0.0.0.0:3000->3000/tcp, [::]:3000->3000/tcp   docker_ci

```


![image_alt](https://github.com/nicolae1993/DevopsSimpleCiCd/blob/541ad7aa28538fc52cdf4ec6a5a714d92b3b6a63/images/DockerWeb.PNG)

![image_alt](https://github.com/nicolae1993/DevopsSimpleCiCd/blob/541ad7aa28538fc52cdf4ec6a5a714d92b3b6a63/images/SecurityGroup.PNG)


![image_alt](https://github.com/nicolae1993/DevopsSimpleCiCd/blob/c7a4ca7072a77785a71c1f1e8b31b752beda1711/images/stageView.PNG)
