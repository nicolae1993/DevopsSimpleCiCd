
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
