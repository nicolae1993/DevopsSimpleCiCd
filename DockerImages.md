
In this pipeline I created the images 

```groovy

        stage("image build"){
            steps{
                sh 'docker image build -t nicolaestan93/docker_ci:v$BUILD_ID /var/lib/jenkins/workspace/ci/getting-started-app-main'
                sh 'docker image tag nicolaestan93/docker_ci:v$BUILD_ID nicolaestan93/ci:latest'
            }

```

```After I run the above pipeline in Jenkins the below image was created with ID 3e8f09d15902. 
Latest has the same ID and it is just a tag.
A Docker tag is essentially a label or alias that points to a specific Docker image.
It’s part of the image name and helps you identify, version, and manage images easily.```

```bash
docker images
                                                                                                                              i Info →   U  In Use
IMAGE                        ID             DISK USAGE   CONTENT SIZE   EXTRA
nicolaestan93/ci:latest      3e8f09d15902        296MB         75.1MB
nicolaestan93/docker_ci:v6   3e8f09d15902        296MB         75.1MB

```


```
+ docker image build -t nicolaestan93/docker_ci:v6 /var/lib/jenkins/workspace/ci/getting-started-app-main
#0 building with "default" instance using docker driver

#1 [internal] load build definition from Dockerfile
#1 transferring dockerfile: 201B done
#1 DONE 0.0s

#2 resolve image config for docker-image://docker.io/docker/dockerfile:1
#2 DONE 1.1s

#3 docker-image://docker.io/docker/dockerfile:1@sha256:b6afd42430b15f2d2a4c5a02b919e98a525b785b1aaff16747d2f623364e39b6
#3 resolve docker.io/docker/dockerfile:1@sha256:b6afd42430b15f2d2a4c5a02b919e98a525b785b1aaff16747d2f623364e39b6 0.0s done
#3 sha256:77246a01651da592b7bae79e0e20ed3b4f2e4c00a1b54b7c921c91ae3fa9ef07 1.05MB / 13.57MB 0.2s
#3 sha256:77246a01651da592b7bae79e0e20ed3b4f2e4c00a1b54b7c921c91ae3fa9ef07 13.57MB / 13.57MB 0.3s
#3 sha256:77246a01651da592b7bae79e0e20ed3b4f2e4c00a1b54b7c921c91ae3fa9ef07 13.57MB / 13.57MB 0.3s done
#3 extracting sha256:77246a01651da592b7bae79e0e20ed3b4f2e4c00a1b54b7c921c91ae3fa9ef07
#3 extracting sha256:77246a01651da592b7bae79e0e20ed3b4f2e4c00a1b54b7c921c91ae3fa9ef07 0.3s done
#3 DONE 0.7s

#4 [internal] load metadata for docker.io/library/node:24-alpine
#4 DONE 1.2s

#5 [internal] load .dockerignore
#5 transferring context: 64B done
#5 DONE 0.0s

#6 [1/4] FROM docker.io/library/node:24-alpine@sha256:7fddd9ddeae8196abf4a3ef2de34e11f7b1a722119f91f28ddf1e99dcafdf114
#6 resolve docker.io/library/node:24-alpine@sha256:7fddd9ddeae8196abf4a3ef2de34e11f7b1a722119f91f28ddf1e99dcafdf114 0.0s done
#6 DONE 0.2s

#7 [internal] load build context
#7 transferring context: 4.57MB 0.1s done
#7 DONE 0.2s

#6 [1/4] FROM docker.io/library/node:24-alpine@sha256:7fddd9ddeae8196abf4a3ef2de34e11f7b1a722119f91f28ddf1e99dcafdf114
#6 sha256:867a770c9b3548b3b2357b54112add9711dd53d8679a3c1bb4c3d9ac675a5c02 0B / 448B 0.2s
#6 sha256:867a770c9b3548b3b2357b54112add9711dd53d8679a3c1bb4c3d9ac675a5c02 448B / 448B 0.3s done
#6 sha256:0653b96c7e89eb8a796a819757fa29a918692669e68f09eac2215c6401407538 0B / 1.26MB 0.2s
#6 sha256:d8573c1c310e7789794576ea96c600be3bb905a6cf0ef787f89922d992d39b78 0B / 51.11MB 0.2s
#6 sha256:589002ba0eaed121a1dbf42f6648f29e5be55d5c8a6ee0f8eaa0285cc21ac153 0B / 3.86MB 0.2s
#6 sha256:0653b96c7e89eb8a796a819757fa29a918692669e68f09eac2215c6401407538 1.26MB / 1.26MB 0.4s done
#6 sha256:d8573c1c310e7789794576ea96c600be3bb905a6cf0ef787f89922d992d39b78 3.15MB / 51.11MB 0.5s
#6 sha256:589002ba0eaed121a1dbf42f6648f29e5be55d5c8a6ee0f8eaa0285cc21ac153 3.86MB / 3.86MB 0.5s done
#6 sha256:d8573c1c310e7789794576ea96c600be3bb905a6cf0ef787f89922d992d39b78 15.73MB / 51.11MB 0.6s
#6 extracting sha256:589002ba0eaed121a1dbf42f6648f29e5be55d5c8a6ee0f8eaa0285cc21ac153
#6 sha256:d8573c1c310e7789794576ea96c600be3bb905a6cf0ef787f89922d992d39b78 25.17MB / 51.11MB 0.8s
#6 sha256:d8573c1c310e7789794576ea96c600be3bb905a6cf0ef787f89922d992d39b78 38.80MB / 51.11MB 0.9s
#6 extracting sha256:589002ba0eaed121a1dbf42f6648f29e5be55d5c8a6ee0f8eaa0285cc21ac153 0.2s done
#6 sha256:d8573c1c310e7789794576ea96c600be3bb905a6cf0ef787f89922d992d39b78 51.11MB / 51.11MB 1.1s
#6 sha256:d8573c1c310e7789794576ea96c600be3bb905a6cf0ef787f89922d992d39b78 51.11MB / 51.11MB 1.1s done
#6 extracting sha256:d8573c1c310e7789794576ea96c600be3bb905a6cf0ef787f89922d992d39b78
#6 extracting sha256:d8573c1c310e7789794576ea96c600be3bb905a6cf0ef787f89922d992d39b78 1.6s done
#6 DONE 2.9s

#6 [1/4] FROM docker.io/library/node:24-alpine@sha256:7fddd9ddeae8196abf4a3ef2de34e11f7b1a722119f91f28ddf1e99dcafdf114
#6 extracting sha256:0653b96c7e89eb8a796a819757fa29a918692669e68f09eac2215c6401407538 0.1s done
#6 extracting sha256:867a770c9b3548b3b2357b54112add9711dd53d8679a3c1bb4c3d9ac675a5c02 0.0s done
#6 DONE 2.9s

#8 [2/4] WORKDIR /app
#8 DONE 0.4s

#9 [3/4] COPY . .
#9 DONE 0.1s

#10 [4/4] RUN npm install --omit=dev
#10 2.574 npm warn deprecated rimraf@3.0.2: Rimraf versions prior to v4 are no longer supported
#10 2.655 npm warn deprecated npmlog@6.0.2: This package is no longer supported.
#10 2.934 npm warn deprecated @npmcli/move-file@1.1.2: This functionality has been moved to @npmcli/fs
#10 2.952 npm warn deprecated are-we-there-yet@3.0.1: This package is no longer supported.
#10 3.112 npm warn deprecated gauge@4.0.4: This package is no longer supported.
#10 4.298 
#10 4.298 added 244 packages, and audited 245 packages in 4s
#10 4.298 
#10 4.299 49 packages are looking for funding
#10 4.299   run `npm fund` for details
#10 4.310 
#10 4.310 10 vulnerabilities (3 low, 7 high)
#10 4.310 
#10 4.310 To address issues that do not require attention, run:
#10 4.310   npm audit fix
#10 4.310 
#10 4.310 To address all issues (including breaking changes), run:
#10 4.310   npm audit fix --force
#10 4.310 
#10 4.310 Run `npm audit` for details.
#10 4.313 npm notice
#10 4.313 npm notice New minor version of npm available! 11.9.0 -> 11.11.1
#10 4.313 npm notice Changelog: https://github.com/npm/cli/releases/tag/v11.11.1
#10 4.313 npm notice To update run: npm install -g npm@11.11.1
#10 4.313 npm notice
#10 DONE 4.5s

#11 exporting to image
#11 exporting layers
#11 exporting layers 2.0s done
#11 exporting manifest sha256:5d24df767db1f3fa5364eb88781659165769ae401e06a0ca841e08f2c8dbaab6 0.0s done
#11 exporting config sha256:2eb4149bba4ae0b59dea258be8ff6e01eb958df8767893d602d473393da172b7 0.0s done
#11 exporting attestation manifest sha256:305e39d117f046455958b7ad29087b9e740559d59814313ee72ae36a84385056 0.0s done
#11 exporting manifest list sha256:3e8f09d159027b08e860d3cac474ee7666df9d9bf8a55091ac761aaab7a08fee 0.0s done
#11 naming to docker.io/nicolaestan93/docker_ci:v6
#11 naming to docker.io/nicolaestan93/docker_ci:v6 done
#11 unpacking to docker.io/nicolaestan93/docker_ci:v6
#11 unpacking to docker.io/nicolaestan93/docker_ci:v6 1.0s done
#11 DONE 3.1s
```
