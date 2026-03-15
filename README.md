# 🚀 CI/CD Pipeline with Jenkins and Docker

This project demonstrates a simple **CI/CD pipeline** using **Jenkins** and **Docker** to build and deploy an open-source application: 
https://github.com/docker/getting-started

## 📌 Project Overview

The repository contains a **Dockerfile** used to build a Docker image for an open-source application.  
The entire build and deployment process is automated using a **Jenkins pipeline**.

## ⚙️ CI/CD Workflow

The pipeline performs the following steps:

1. **Source Code Checkout**
   - Jenkins connects to the GitHub repository and downloads the latest version of the code.

2. **Build Docker Image**
   - Jenkins builds a Docker image using the `Dockerfile` included in the repository.

3. **Tag Docker Image**
   - The image is tagged with the Jenkins **BUILD_ID** and also with the `latest` tag.

4. **Push Image to Docker Hub**
   - The built image is pushed to **Docker Hub**, making it available for deployment anywhere.

5. **Run Docker Container**
   - Jenkins runs a container using the latest version of the Docker image.

## 🐳 Technologies Used

- **Jenkins** – CI/CD automation
- **Docker** – Containerization
- **Docker Hub** – Image registry
- **GitHub** – Source code hosting

## ▶️ Example Docker Run Command

```bash
docker run -itd --name docker_ci -p 3000:3000 nicolaestan93/docker_ci:latest
```






```bash
 systemctl status jenkins
● jenkins.service - Jenkins Continuous Integration Server
     Loaded: loaded (/usr/lib/systemd/system/jenkins.service; enabled; preset: enabled)
     Active: active (running) since Sun 2026-03-15 09:32:22 UTC; 2h 40min ago
   Main PID: 534 (java)
      Tasks: 48 (limit: 4522)
     Memory: 826.2M (peak: 847.9M)
        CPU: 2min 35.190s
     CGroup: /system.slice/jenkins.service
             └─534 /usr/bin/java -Djava.awt.headless=true -jar /usr/share/java/jenkins.war --webroot=/var/cache/jenkins/war --httpPort=8080




systemctl status docker
● docker.service - Docker Application Container Engine
     Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; preset: enabled)
     Active: active (running) since Sun 2026-03-15 09:32:08 UTC; 2h 21min ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 765 (dockerd)
      Tasks: 24
     Memory: 144.4M (peak: 172.5M)
        CPU: 9.668s
     CGroup: /system.slice/docker.service
             ├─ 765 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
             ├─4442 /usr/bin/docker-proxy -proto tcp -host-ip 0.0.0.0 -host-port 3000 -container-ip 172.17.0.2 -container-port 3000 -use-listen-fd
             └─4450 /usr/bin/docker-proxy -proto tcp -host-ip :: -host-port 3000 -container-ip 172.17.0.2 -container-port 3000 -use-listen-fd
```


Setup the webhook to Jenkins URL 

![image_alt](https://github.com/nicolae1993/DevopsSimpleCiCd/blob/c207c63572cfc5074d2c44f5677090fc2d9ddbdf/images/Capture.PNG)

After running this groovy pipeline the Github project was brought to Jenkins server

```groovy
    stages{
        stage("Code checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/nicolae1993/DevopsSimpleCiCd.git'
            }
        }
```
        
```  Below the Jenkins server where you can see the content of the project from Github```

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
