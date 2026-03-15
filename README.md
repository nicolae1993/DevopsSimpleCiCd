# DevopsSimpleCiCd

```bash
jenkins.service - Jenkins Continuous Integration Server
     Loaded: loaded (/usr/lib/systemd/system/jenkins.service; enabled; preset: enabled)
     Active: active (running) since Sun 2026-03-15 07:24:19 UTC; 2min 4s ago
   Main PID: 3955 (java)
      Tasks: 37 (limit: 1006)
     Memory: 308.9M (peak: 330.2M)
        CPU: 20.976s
     CGroup: /system.slice/jenkins.service
             └─3955 /usr/bin/java -Djava.awt.headless=true -jar /usr/share/java/jenkins.war --webroot=/var/cache/jenkins/war --httpPort=8080

Mar 15 07:24:13 ip-172-31-40-116 jenkins[3955]: [LF]> This may also be found at: /var/lib/jenkins/secrets/initialAdminPassword
Mar 15 07:24:13 ip-172-31-40-116 jenkins[3955]: [LF]>
Mar 15 07:24:13 ip-172-31-40-116 jenkins[3955]: [LF]> *************************************************************
Mar 15 07:24:13 ip-172-31-40-116 jenkins[3955]: [LF]> *************************************************************
Mar 15 07:24:13 ip-172-31-40-116 jenkins[3955]: [LF]> *************************************************************
Mar 15 07:24:19 ip-172-31-40-116 jenkins[3955]: 2026-03-15 07:24:19.022+0000 [id=32]        INFO        jenkins.InitReactorRunner$1#onAttained: C>
Mar 15 07:24:19 ip-172-31-40-116 jenkins[3955]: 2026-03-15 07:24:19.042+0000 [id=24]        INFO        hudson.lifecycle.Lifecycle#onReady: Jenki>
Mar 15 07:24:19 ip-172-31-40-116 systemd[1]: Started jenkins.service - Jenkins Continuous Integration Server.
Mar 15 07:24:19 ip-172-31-40-116 jenkins[3955]: 2026-03-15 07:24:19.648+0000 [id=50]        INFO        h.m.DownloadService$Downloadable#load: Ob>
Mar 15 07:24:19 ip-172-31-40-116 jenkins[3955]: 2026-03-15 07:24:19.649+0000 [id=50]        INFO        hudson.util.Retrier#start: Performed the


```


Setup the webhook to Jenkins URL 

![image_alt](https://github.com/nicolae1993/DevopsSimpleCiCd/blob/c207c63572cfc5074d2c44f5677090fc2d9ddbdf/images/Capture.PNG)

After running this groovy pipeline the project was brought to Jenkins server

```groovy
    stages{
        stage("Code checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/nicolae1993/DevopsSimpleCiCd.git'
            }
        }
```
        

```bash
/var/lib/jenkins/workspace/ci/getting-started-app-main$ ll
total 152
drwxr-xr-x 4 jenkins jenkins   4096 Mar 15 09:48 ./
drwxr-xr-x 5 jenkins jenkins   4096 Mar 15 09:48 ../
-rw-r--r-- 1 jenkins jenkins     24 Mar 15 07:48 .dockerignore
-rw-r--r-- 1 jenkins jenkins    162 Mar 15 09:48 Dockerfile
-rw-r--r-- 1 jenkins jenkins    269 Mar 15 07:48 README.md
-rw-r--r-- 1 jenkins jenkins 118912 Mar 15 07:48 package-lock.json
-rw-r--r-- 1 jenkins jenkins    541 Mar 15 07:48 package.json
drwxr-xr-x 4 jenkins jenkins   4096 Mar 15 07:48 spec/
drwxr-xr-x 5 jenkins jenkins   4096 Mar 15 07:48 src/

```
