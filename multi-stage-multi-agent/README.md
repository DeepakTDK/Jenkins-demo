# Job

Set up a multi stage jenkins pipeline where each stage is run on a unique agent. This is a very useful approach when you have multi language application or application that has conflicting dependencies.

# Console Output

Started by user Deepak
Obtained multi-stage-multi-agent/Jenkinsfile from git https://github.com/DeepakTDK/Jenkins-demo
[Pipeline] Start of Pipeline
[Pipeline] stage
[Pipeline] { (Back-end)
[Pipeline] node333
Running on Jenkins in /var/lib/jenkins/workspace/first-jenkins-job
[Pipeline] {
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/first-jenkins-job/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/DeepakTDK/Jenkins-demo # timeout=10
Fetching upstream changes from https://github.com/DeepakTDK/Jenkins-demo
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/DeepakTDK/Jenkins-demo +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision be2a7c0be760524858bd774969d917d76adab512 (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f be2a7c0be760524858bd774969d917d76adab512 # timeout=10
Commit message: "Create Jenkinsfile"
 > git rev-list --no-walk 61a448845e0a7d0076ef84adb068a8ae594c310a # timeout=10
[Pipeline] withEnv
[Pipeline] {
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ docker inspect -f . maven:3.8.1-adoptopenjdk-11

Error: No such object: maven:3.8.1-adoptopenjdk-11
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ docker pull maven:3.8.1-adoptopenjdk-11
3.8.1-adoptopenjdk-11: Pulling from library/maven
16ec32c2132b: Pulling fs layer
3f63509f5b97: Pulling fs layer
34d7b43f221b: Pulling fs layer
a1931e18ae45: Pulling fs layer
20904a3b2df7: Pulling fs layer
fb5c0685f15f: Pulling fs layer
a18abadafb9a: Pulling fs layer
20904a3b2df7: Waiting
fb5c0685f15f: Waiting
a18abadafb9a: Waiting
a1931e18ae45: Waiting
3f63509f5b97: Download complete
16ec32c2132b: Verifying Checksum
16ec32c2132b: Download complete
20904a3b2df7: Download complete
fb5c0685f15f: Verifying Checksum
fb5c0685f15f: Download complete
a1931e18ae45: Verifying Checksum
a1931e18ae45: Download complete
a18abadafb9a: Verifying Checksum
a18abadafb9a: Download complete
16ec32c2132b: Pull complete
3f63509f5b97: Pull complete
34d7b43f221b: Verifying Checksum
34d7b43f221b: Download complete
34d7b43f221b: Pull complete
a1931e18ae45: Pull complete
20904a3b2df7: Pull complete
fb5c0685f15f: Pull complete
a18abadafb9a: Pull complete
Digest: sha256:143ff7942b5ef5a004252405a31fa2813dfa438f08494fad1757029de5f64082
Status: Downloaded newer image for maven:3.8.1-adoptopenjdk-11
docker.io/library/maven:3.8.1-adoptopenjdk-11
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] withDockerContainer
Jenkins does not seem to be running inside a container
$ docker run -t -d -u 129:137 -w /var/lib/jenkins/workspace/first-jenkins-job -v /var/lib/jenkins/workspace/first-jenkins-job:/var/lib/jenkins/workspace/first-jenkins-job:rw,z -v /var/lib/jenkins/workspace/first-jenkins-job@tmp:/var/lib/jenkins/workspace/first-jenkins-job@tmp:rw,z -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** maven:3.8.1-adoptopenjdk-11 cat
$ docker top 8ae7579a084d2ed5d06491d6969c346e7f7563830b2d7cd5dd2b81ebebc95cee -eo pid,comm
[Pipeline] {
[Pipeline] sh
+ mvn --version
Apache Maven 3.8.1 (05c21c65bdfed0f71a2f2ada8b84da59348c4c5d)
Maven home: /usr/share/maven
Java version: 11.0.11, vendor: AdoptOpenJDK, runtime: /opt/java/openjdk
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "6.2.0-36-generic", arch: "amd64", family: "unix"
[Pipeline] }
$ docker stop --time=1 8ae7579a084d2ed5d06491d6969c346e7f7563830b2d7cd5dd2b81ebebc95cee
$ docker rm -f --volumes 8ae7579a084d2ed5d06491d6969c346e7f7563830b2d7cd5dd2b81ebebc95cee
[Pipeline] // withDockerContainer
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Front-end)
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/first-jenkins-job
[Pipeline] {
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/first-jenkins-job/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/DeepakTDK/Jenkins-demo # timeout=10
Fetching upstream changes from https://github.com/DeepakTDK/Jenkins-demo
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/DeepakTDK/Jenkins-demo +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision be2a7c0be760524858bd774969d917d76adab512 (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f be2a7c0be760524858bd774969d917d76adab512 # timeout=10
Commit message: "Create Jenkinsfile"
[Pipeline] withEnv
[Pipeline] {
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ docker inspect -f . node:16-alpine
.
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] withDockerContainer
Jenkins does not seem to be running inside a container
$ docker run -t -d -u 129:137 -w /var/lib/jenkins/workspace/first-jenkins-job -v /var/lib/jenkins/workspace/first-jenkins-job:/var/lib/jenkins/workspace/first-jenkins-job:rw,z -v /var/lib/jenkins/workspace/first-jenkins-job@tmp:/var/lib/jenkins/workspace/first-jenkins-job@tmp:rw,z -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** node:16-alpine cat
$ docker top 5c8c630fd12b7da5f91d2b8ab4f8e0fc857b6b846865dac3bf40d73ab69f2431 -eo pid,comm
[Pipeline] {
[Pipeline] sh
+ node --version
v16.20.2
[Pipeline] }
$ docker stop --time=1 5c8c630fd12b7da5f91d2b8ab4f8e0fc857b6b846865dac3bf40d73ab69f2431
$ docker rm -f --volumes 5c8c630fd12b7da5f91d2b8ab4f8e0fc857b6b846865dac3bf40d73ab69f2431
[Pipeline] // withDockerContainer
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (db)
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/first-jenkins-job
[Pipeline] {
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/first-jenkins-job/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/DeepakTDK/Jenkins-demo # timeout=10
Fetching upstream changes from https://github.com/DeepakTDK/Jenkins-demo
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/DeepakTDK/Jenkins-demo +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision be2a7c0be760524858bd774969d917d76adab512 (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f be2a7c0be760524858bd774969d917d76adab512 # timeout=10
Commit message: "Create Jenkinsfile"
[Pipeline] withEnv
[Pipeline] {
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ docker inspect -f . mysql:latest

Error: No such object: mysql:latest
[Pipeline] isUnix
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ docker pull mysql:latest
latest: Pulling from library/mysql
8e0176adc18c: Pulling fs layer
2d2c52718f65: Pulling fs layer
d88d03ce139b: Pulling fs layer
4a7d7f11aa1e: Pulling fs layer
ce5949193e4c: Pulling fs layer
f7f024dfb329: Pulling fs layer
5fc3c840facc: Pulling fs layer
509068e49488: Pulling fs layer
cbc847bab598: Pulling fs layer
942bef62a146: Pulling fs layer
4a7d7f11aa1e: Waiting
ce5949193e4c: Waiting
f7f024dfb329: Waiting
5fc3c840facc: Waiting
509068e49488: Waiting
cbc847bab598: Waiting
942bef62a146: Waiting
2d2c52718f65: Download complete
d88d03ce139b: Download complete
4a7d7f11aa1e: Verifying Checksum
4a7d7f11aa1e: Download complete
ce5949193e4c: Verifying Checksum
ce5949193e4c: Download complete
f7f024dfb329: Download complete
509068e49488: Download complete
8e0176adc18c: Verifying Checksum
8e0176adc18c: Download complete
942bef62a146: Verifying Checksum
942bef62a146: Download complete
8e0176adc18c: Pull complete
2d2c52718f65: Pull complete
5fc3c840facc: Verifying Checksum
5fc3c840facc: Download complete
d88d03ce139b: Pull complete
4a7d7f11aa1e: Pull complete
ce5949193e4c: Pull complete
f7f024dfb329: Pull complete
cbc847bab598: Verifying Checksum
cbc847bab598: Download complete
5fc3c840facc: Pull complete
509068e49488: Pull complete
cbc847bab598: Pull complete
942bef62a146: Pull complete
Digest: sha256:1773f3c7aa9522f0014d0ad2bbdaf597ea3b1643c64c8ccc2123c64afd8b82b1
Status: Downloaded newer image for mysql:latest
docker.io/library/mysql:latest
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] withDockerContainer
Jenkins does not seem to be running inside a container
$ docker run -t -d -u 129:137 -w /var/lib/jenkins/workspace/first-jenkins-job -v /var/lib/jenkins/workspace/first-jenkins-job:/var/lib/jenkins/workspace/first-jenkins-job:rw,z -v /var/lib/jenkins/workspace/first-jenkins-job@tmp:/var/lib/jenkins/workspace/first-jenkins-job@tmp:rw,z -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** mysql:latest cat
$ docker top a61b3ff2480033af35b417c855cd3161d16b0b55b42726dc2ec9fc105600ca65 -eo pid,comm
[Pipeline] {
[Pipeline] sh
/var/lib/jenkins/workspace/first-jenkins-job@tmp/durable-e5b470e8/script.sh: line 1: syntax error near unexpected token `from'
[Pipeline] }
$ docker stop --time=1 a61b3ff2480033af35b417c855cd3161d16b0b55b42726dc2ec9fc105600ca65
$ docker rm -f --volumes a61b3ff2480033af35b417c855cd3161d16b0b55b42726dc2ec9fc105600ca65
[Pipeline] // withDockerContainer
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // stage
[Pipeline] End of Pipeline
# Finished: SUCCESS
