# systems
ubuntu@ip-172-31-35-224:~$ client_loop: send disconnect: Connection reset by peer

PuvvulaM@HBADT4401133 MINGW64 ~/Downloads
$ ssh -i "july20.pem" ubuntu@ec2-3-15-213-181.us-east-2.compute.amazonaws.com
buntu@ip-172-31-35-224:~$ vi dockerfile
ubuntu@ip-172-31-35-224:~$ sudo docker build .
ubuntu@ip-172-31-35-224:~$ touch asdf
ubuntu@ip-172-31-35-224:~$ sudo docker build . -t "first"
Sending build context to Docker daemon  15.87kB
Step 1/4 : FROM ubuntu:18.04
 ---> 6526a1858e5d
Step 2/4 : COPY ./asdf /asdf
 ---> 7b5b183394ba
Step 3/4 : RUN echo "hello"
 ---> Running in 1bb15c8f83f4
hello
Removing intermediate container 1bb15c8f83f4
 ---> 30e78aa05d14
Step 4/4 : CMD apt-get update
 ---> Running in 92fa80843289
Removing intermediate container 92fa80843289
 ---> 00f5fe9697e0
Successfully built 00f5fe9697e0
Successfully tagged first:latest
ubuntu@ip-172-31-35-224:~$ sudo docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
first               latest              00f5fe9697e0        17 seconds ago      64.2MB
ubuntu              18.04               6526a1858e5d        13 days ago         64.2MB
ubuntu@ip-172-31-35-224:~$ sudo docker rm first
Error: No such container: first
ubuntu@ip-172-31-35-224:~$ sudo docker rmi first
Untagged: first:latest
Deleted: sha256:00f5fe9697e07ba0f4f795fc824906a4d223040b3db9d81de421f02d0558d753
Deleted: sha256:30e78aa05d14dcadcfaa08494b6ca550d6720c5a4ccee7999bdf01c325007055
Deleted: sha256:7b5b183394ba26a00bc8e2afe60b345cac7b56dd0152d86e630da78fbc0bb2eb
Deleted: sha256:bf71e18281524f3bc27d100dda8137fa71934da49db8a50c46a275e9fcb3b4b4
ubuntu@ip-172-31-35-224:~$ sudo docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
ubuntu              18.04               6526a1858e5d        13 days ago         64.2MB
ubuntu@ip-172-31-35-224:~$ sudo docker build .
Sending build context to Docker daemon  15.87kB
Step 1/4 : FROM ubuntu:18.04
 ---> 6526a1858e5d
Step 2/4 : COPY ./asdf /asdf
 ---> 3d254b79ed55
Step 3/4 : RUN echo "hello"
 ---> Running in c9588871670a
hello
Removing intermediate container c9588871670a
 ---> 48f8c7188384
Step 4/4 : CMD apt-get update
 ---> Running in c53596ed84eb
Removing intermediate container c53596ed84eb
 ---> d5f1ec368b72
Successfully built d5f1ec368b72
ubuntu@ip-172-31-35-224:~$ sudo docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
<none>              <none>              d5f1ec368b72        6 seconds ago       64.2MB
ubuntu              18.04               6526a1858e5d        13 days ago         64.2MB
ubuntu@ip-172-31-35-224:~$ sudo docker rmi d5f1ec368b72
Deleted: sha256:d5f1ec368b72b764592cb49179612cdaea3670c63afc42e703d96cc76cf1ca81
Deleted: sha256:48f8c71883846eae5f67a0cfe3f3fb5bc3c3e8ba26ea103c1ded48753c375de1
Deleted: sha256:3d254b79ed55e1b442e1e1dd0491bdd644e901c923976edc9eaffbe08ec12621
Deleted: sha256:bf71e18281524f3bc27d100dda8137fa71934da49db8a50c46a275e9fcb3b4b4
ubuntu@ip-172-31-35-224:~$ sudo docker build . -t "first"
Sending build context to Docker daemon  15.87kB
Step 1/4 : FROM ubuntu:18.04
 ---> 6526a1858e5d
Step 2/4 : COPY ./asdf /asdf
 ---> 40ddd834b652
Step 3/4 : RUN echo "hello"
 ---> Running in f3bc9d24f8b6
hello
Removing intermediate container f3bc9d24f8b6
 ---> 83a8edceb0f1
Step 4/4 : CMD apt-get update
 ---> Running in cab1e137d6de
Removing intermediate container cab1e137d6de
 ---> 37597ab9c028
Successfully built 37597ab9c028
Successfully tagged first:latest
ubuntu@ip-172-31-35-224:~$ sudo docker run first -d --name first
docker: Error response from daemon: OCI runtime create failed: container_linux.go:349: starting container process caused "exec: \"-d\": executable file not found in $PATH": unknown.
ubuntu@ip-172-31-35-224:~$ sudo docker run  -d first
972e969b525a0e448f356e7b8c59974e58eb8342c82515c4b04a7bceaed87ef5
ubuntu@ip-172-31-35-224:~$ sudo docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
ubuntu@ip-172-31-35-224:~$ sudo docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                      PORTS               NAMES
972e969b525a        first               "/bin/sh -c 'apt-get…"   17 seconds ago      Exited (0) 12 seconds ago                       serene_kepler
4bc38969c926        first               "-d --name first"        39 seconds ago      Created                                         epic_kare
ubuntu@ip-172-31-35-224:~$ sudo docker rm 972e969b525a
972e969b525a
ubuntu@ip-172-31-35-224:~$ sudo docker rm 4bc38969c926
4bc38969c926
ubuntu@ip-172-31-35-224:~$ sudo docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
ubuntu@ip-172-31-35-224:~$
ubuntu@ip-172-31-35-224:~$
ubuntu@ip-172-31-35-224:~$
ubuntu@ip-172-31-35-224:~$ sudo docker run -d --name first first
50b6071047fee51aa281b8d3fcaff669b7d1a242ad9360778b576f30c2c0f98b
ubuntu@ip-172-31-35-224:~$ sudo docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
ubuntu@ip-172-31-35-224:~$ sudo docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                     PORTS               NAMES
50b6071047fe        first               "/bin/sh -c 'apt-get…"   11 seconds ago      Exited (0) 6 seconds ago                       first
ubuntu@ip-172-31-35-224:~$ sudo rm first
rm: cannot remove 'first': No such file or directory
ubuntu@ip-172-31-35-224:~$ sudo docker rm gfirst
Error: No such container: gfirst
ubuntu@ip-172-31-35-224:~$ sudo docker rm first
first
ubuntu@ip-172-31-35-224:~$ sudo docker rmi first
Untagged: first:latest
Deleted: sha256:37597ab9c0285a56e366092a301588880edbd485c67a8f6d06a78d9787e9870b
Deleted: sha256:83a8edceb0f14885f031a67d0c8a3823c525ea63c8f17b730d1eef5d7c755206
Deleted: sha256:40ddd834b652ec86175fbf2656b7dcfa982dc253b01b226c7f7ef64e2135b504
Deleted: sha256:bf71e18281524f3bc27d100dda8137fa71934da49db8a50c46a275e9fcb3b4b4
ubuntu@ip-172-31-35-224:~$ vi dockerfile
ubuntu@ip-172-31-35-224:~$ sudo docker build . -t "first"
Sending build context to Docker daemon  16.38kB
Step 1/3 : FROM ubuntu:18.04
 ---> 6526a1858e5d
Step 2/3 : COPY ./asdf /asdf
 ---> 443849fa6199
Step 3/3 : RUN echo "hello"
 ---> Running in 0207e0000ffa
hello
Removing intermediate container 0207e0000ffa
 ---> 4c2c37b34803
Successfully built 4c2c37b34803
Successfully tagged first:latest
ubuntu@ip-172-31-35-224:~$ sudo docker run -d --name first first
6bb76316392731973a9e5d2f8b9f274284555300b3c13b85032995bdf3177731
ubuntu@ip-172-31-35-224:~$ sudo cocker ps -a
sudo: cocker: command not found
ubuntu@ip-172-31-35-224:~$ sudo docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
6bb763163927        first               "/bin/bash"         15 seconds ago      Exited (0) 14 seconds ago                       first
ubuntu@ip-172-31-35-224:~$ sudo docker rmi first
Error response from daemon: conflict: unable to remove repository reference "first" (must force) - container 6bb763163927 is using its referenced image 4c2c37b34803
ubuntu@ip-172-31-35-224:~$ sudo rm first
rm: cannot remove 'first': No such file or directory
ubuntu@ip-172-31-35-224:~$ sudo docker rm first
first
ubuntu@ip-172-31-35-224:~$ sudo docker rmi first
Untagged: first:latest
Deleted: sha256:4c2c37b34803f45468142768c26b5182aec0b05e1d86e2351b340f0029ccc4de
Deleted: sha256:443849fa61991f59d32ea90f6bc806d1ae96b6958241b89b5283e0b493ebff11
Deleted: sha256:bf71e18281524f3bc27d100dda8137fa71934da49db8a50c46a275e9fcb3b4b4
ubuntu@ip-172-31-35-224:~$ vi dockerfile
ubuntu@ip-172-31-35-224:~$ sudo docker build . -t "first"
Sending build context to Docker daemon   16.9kB
Error response from daemon: No build stage in current context
ubuntu@ip-172-31-35-224:~$ sudo docker build . -t "first"
Sending build context to Docker daemon   16.9kB
Error response from daemon: No build stage in current context
ubuntu@ip-172-31-35-224:~$ sudo docker volumes
docker: 'volumes' is not a docker command.
See 'docker --help'
ubuntu@ip-172-31-35-224:~$ sudo docker volume

Usage:  docker volume COMMAND

Manage volumes

Commands:
  create      Create a volume
  inspect     Display detailed information on one or more volumes
  ls          List volumes
  prune       Remove all unused local volumes
  rm          Remove one or more volumes

Run 'docker volume COMMAND --help' for more information on a command.
ubuntu@ip-172-31-35-224:~$ sudo docker volumes
docker: 'volumes' is not a docker command.
See 'docker --help'
ubuntu@ip-172-31-35-224:~$ sudo docker v--help
docker: 'v--help' is not a docker command.
See 'docker --help'
ubuntu@ip-172-31-35-224:~$ sudo docker --help

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Options:
      --config string      Location of client config files (default "/home/ubuntu/.docker")
  -c, --context string     Name of the context to use to connect to the daemon (overrides DOCKER_HOST env var and default context set with "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level ("debug"|"info"|"warn"|"error"|"fatal") (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default "/home/ubuntu/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default "/home/ubuntu/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default "/home/ubuntu/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Management Commands:
  builder     Manage builds
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  engine      Manage the docker engine
  image       Manage images
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes

Run 'docker COMMAND --help' for more information on a command.
ubuntu@ip-172-31-35-224:~$ sudo docker volume

Usage:  docker volume COMMAND

Manage volumes

Commands:
  create      Create a volume
  inspect     Display detailed information on one or more volumes
  ls          List volumes
  prune       Remove all unused local volumes
  rm          Remove one or more volumes

Run 'docker volume COMMAND --help' for more information on a command.
ubuntu@ip-172-31-35-224:~$ sudo docker volume ls
DRIVER              VOLUME NAME
ubuntu@ip-172-31-35-224:~$ history
    1  vi dockerfile
    2  sudo docker build .
    3  touch asdf
    4  sudo docker build . -t "first"
    5  sudo docker images
    6  sudo docker rm first
    7  sudo docker rmi first
    8  sudo docker images
    9  sudo docker build .
   10  sudo docker images
   11  sudo docker rmi d5f1ec368b72
   12  sudo docker build . -t "first"
   13  sudo docker run first -d --name first
   14  sudo docker run  -d first
   15  sudo docker ps
   16  sudo docker ps -a
   17  sudo docker rm 972e969b525a
   18  sudo docker rm 4bc38969c926
   19  sudo docker ps -a
   20  sudo docker run -d --name first first
   21  sudo docker ps
   22  sudo docker ps -a
   23  sudo rm first
   24  sudo docker rm gfirst
   25  sudo docker rm first
   26  sudo docker rmi first
   27  vi dockerfile
   28  sudo docker build . -t "first"
   29  sudo docker run -d --name first first
   30  sudo cocker ps -a
   31  sudo docker ps -a
   32  sudo docker rmi first
   33  sudo rm first
   34  sudo docker rm first
   35  sudo docker rmi first
   36  vi dockerfile
   37  sudo docker build . -t "first"
   38  sudo docker volumes
   39  sudo docker volume
   40  sudo docker volumes
   41  sudo docker v--help
   42  sudo docker --help
   43  sudo docker volume
   44  sudo docker volume ls
   45  history
ubuntu@ip-172-31-35-224:~$ client_loop: send disconnect: Connection reset by peer

PuvvulaM@HBADT4401133 MINGW64 ~/Downloads
$ ssh -i "july20.pem" ubuntu@ec2-3-15-213-181.us-east-2.compute.amazonaws.com
vi vasufilrWelcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.3.0-1032-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Wed Sep  2 17:18:28 UTC 2020

  System load:  0.0               Processes:              104
  Usage of /:   22.1% of 7.69GB   Users logged in:        1
  Memory usage: 27%               IP address for eth0:    172.31.35.224
  Swap usage:   0%                IP address for docker0: 172.17.0.1


34 packages can be updated.
21 updates are security updates.


Last login: Wed Sep  2 16:53:03 2020 from 106.217.146.205
ubuntu@ip-172-31-35-224:~$ vi vasufile
ubuntu@ip-172-31-35-224:~$ ls
asdf  dockerfile  vasufile
ubuntu@ip-172-31-35-224:~$ cat dockerfile
COPY ./asdf /asdf
RUN echo "hello"
ubuntu@ip-172-31-35-224:~$ ^C
ubuntu@ip-172-31-35-224:~$ vi vasufile
ubuntu@ip-172-31-35-224:~$ sudo docker build . -t "second"
Sending build context to Docker daemon  19.97kB
Error response from daemon: No build stage in current context
ubuntu@ip-172-31-35-224:~$ sudo docker build . -t "vasufile"
Sending build context to Docker daemon  19.97kB
Error response from daemon: No build stage in current context
ubuntu@ip-172-31-35-224:~$ sudo build .
sudo: build: command not found
ubuntu@ip-172-31-35-224:~$ sudo build . client_loop: send disconnect: Connection reset by peer

----------------------------------------------
$ ssh -i "awsnew.pem" ubuntu@ec2-18-191-200-110.us-east-2.compute.amazonaws.com
ubuntu@ip-172-31-13-163:~$ export JAVA_HOME=/usr/lib/jvm/java-8-openjdk
ubuntu@ip-172-31-13-163:~$ export PATH=$PATH:/usr/lib/jvm/java-8-openjdk/bin
ubuntu@ip-172-31-13-163:~$ sudo apt-get install openjdk-8-jdk
ubuntu@ip-172-31-13-163:~$ export JAVA_HOME=/usr/lib/jvm/java-8-openjdk
ubuntu@ip-172-31-13-163:~$ export PATH=$PATH:/usr/lib/jvm/java-8-openjdk/bin
ubuntu@ip-172-31-13-163:~$ java -version
Jenkins
ubuntu@ip-172-31-13-163:~$ wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
ubuntu@ip-172-31-13-163:~$ sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
ubuntu@ip-172-31-13-163:~$ sudo apt update
ubuntu@ip-172-31-13-163:~$ sudo su jenkins
jenkins@ip-172-31-13-163:~$ cat /var/lib/jenkins/secrets/initialAdminPassword
http://13.58.117.5:8080-vasu jenkins--
Groovy pipeline script

checkout
sonarqube--changes in properties.xml
build
delivery-directly storing from server
deploy--run the upon the server is 
.tar.gz


http://13.58.117.5:8080/

installation of sonarqube

sudo adduser --system --no-create-home --group --disabled-login sonarqube
sudo mkdir /opt/sonarqube
sudo apt-get install unzip
sudo mysql -u root -p
cd /opt/sonarqube
sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-7.5.zip
sudo unzip sonarqube-7.5.zip



ubuntu@ip-172-31-24-215:~$ cd
ubuntu@ip-172-31-24-215:~$ sudo su
root@ip-172-31-24-215:/home/ubuntu# cd
root@ip-172-31-24-215:~#  cd /var/www/html/
root@ip-172-31-24-215:/var/www/html# mv index.nginx-debian.html download.html
root@ip-172-31-24-215:/var/www/html# vi download.html
-----------------------------------
adding key pair to the instance 
3.134.86.125:8080
ssh -i "manoj.pem" ubuntu@ec2-3-134-86-125.us-east-2.compute.amazonaws.com

ssh -i "awsnew.pem" ubuntu@ec2-18-221-104-67.us-east-2.compute.amazonaws.com
http://18.223.0.85:8080---vasu
sudo apt-get update---to download package information from all configured sources.
sudo apt-get install openjdk-8-jdk
sudo apt install default-jdk
JAVA PATH
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export PATH=$PATH:/usr/lib/jvm/java-11-openjdk-amd64/bin
javac -version
Jenkins installation
wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install jenkins
ubuntu@ip-172-31-39-83:~$ sudo su jenkins
jenkins@ip-172-31-39-83:/home/ubuntu$ cd
jenkins@ip-172-31-39-83:~$ pwd
/var/lib/jenkins
jenkins@ip-172-31-39-83:~$ mkdir .ssh
jenkins@ip-172-31-39-83:~$
jenkins@ip-172-31-39-83:~$ cd .ssh
jenkins@ip-172-31-39-83:~/.ssh$ ssh-keygen

cat /var/lib/jenkins/secrets/initialAdminPassword
http://18.191.200.110:8080/login?from=%2F
Maven:

 sudo apt install maven
 export M2_HOME=/opt/maven
 export MAVEN_HOME=/opt/maven
 export PATH=${M2_HOME}/bin:${PATH}
 maven -version

wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz -P /tmp

vi authorized_keys
ubuntu@ip-172-31-16-80:~/.ssh$ chmod 755 id_rsa*
ubuntu@ip-172-31-16-80:~/.ssh$ chmod 400 authorized_keys
ubuntu@ip-172-31-16-80:~/.ssh$ cat id_rsa--private key

ubuntu@ip-172-31-38-194:~$ sudo su jenkins
jenkins@ip-172-31-38-194:/home/ubuntu$ cd /var/lib/jenkins/workspace/
jenkins@ip-172-31-38-194:~/workspace$ cd
jenkins@ip-172-31-38-194:~$ aws configure
AWS Access Key ID [None]: AKIARMW5HRS4QKRXNC4P
AWS Secret Access Key [None]: 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
Default region name [None]: us-west-2
Default output format [None]: table
jenkins@ip-172-31-38-194:~$


aws s3 cp /var/lib/jenkins/workspace/tyuio/target/*.jar s3://vasu2


aws s3 cp a.txt s3://vasu2--- to copy a file into s3 bucket


vasugopi999@gmail.com
Bunny@123

node {
    stage "Create build output"
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '090b8705-028c-41d8-b4e7-9e8ca6fe8c86', url: 'git@ssh.dev.azure.com:v3/deep16134/demo/mvnrepo']]])
    stage "Build"
    sh "mvn clean package"
    stage "s3"
    sh " aws s3 cp /var/lib/jenkins/workspace/asdf/target/*jar s3://vasu2"
    }

Internet Gateway

public IP


Nat gateway

routing table-- route
subnet-- configuration


NAT Gateway

network-add vpc
subnet-- add public\private
dhcp- enable/disable


adding key pair to the instance 
3.134.86.125:8080
ssh -i "manoj.pem" ubuntu@ec2-3-134-86-125.us-east-2.compute.amazonaws.com

ssh -i "awsnew.pem" ubuntu@ec2-18-221-104-67.us-east-2.compute.amazonaws.com
http://18.223.0.85:8080---vasu
sudo apt-get update---to download package information from all configured sources.
sudo apt-get install openjdk-8-jdk
sudo apt install default-jdk
JAVA PATH
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export PATH=$PATH:/usr/lib/jvm/java-11-openjdk-amd64/bin
javac -version
Jenkins installation
wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install jenkins
ubuntu@ip-172-31-39-83:~$ sudo su jenkins
jenkins@ip-172-31-39-83:/home/ubuntu$ cd
jenkins@ip-172-31-39-83:~$ pwd
/var/lib/jenkins
jenkins@ip-172-31-39-83:~$ mkdir .ssh
jenkins@ip-172-31-39-83:~$
jenkins@ip-172-31-39-83:~$ cd .ssh
jenkins@ip-172-31-39-83:~/.ssh$ ssh-keygen

cat /var/lib/jenkins/secrets/initialAdminPassword
http://18.191.200.110:8080/login?from=%2F
Maven:

 sudo apt install maven
 export M2_HOME=/opt/maven
 export MAVEN_HOME=/opt/maven
 export PATH=${M2_HOME}/bin:${PATH}
 maven -version

wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz -P /tmp

vi authorized_keys
ubuntu@ip-172-31-16-80:~/.ssh$ chmod 755 id_rsa*
ubuntu@ip-172-31-16-80:~/.ssh$ chmod 400 authorized_keys
ubuntu@ip-172-31-16-80:~/.ssh$ cat id_rsa--private key

ubuntu@ip-172-31-38-194:~$ sudo su jenkins
jenkins@ip-172-31-38-194:/home/ubuntu$ cd /var/lib/jenkins/workspace/
jenkins@ip-172-31-38-194:~/workspace$ cd
jenkins@ip-172-31-38-194:~$ aws configure
AWS Access Key ID [None]: AKIARMW5HRS4QKRXNC4P
AWS Secret Access Key [None]: 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
Default region name [None]: us-west-2
Default output format [None]: table
jenkins@ip-172-31-38-194:~$


aws s3 cp /var/lib/jenkins/workspace/tyuio/target/*.jar s3://vasu2


aws s3 cp a.txt s3://vasu2--- to copy a file into s3 bucket


vasugopi999@gmail.com
Bunny@123

node {
    stage "Create build output"
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '090b8705-028c-41d8-b4e7-9e8ca6fe8c86', url: 'git@ssh.dev.azure.com:v3/deep16134/demo/mvnrepo']]])
    stage "Build"
    sh "mvn clean package"
    stage "s3"
    sh " aws s3 cp /var/lib/jenkins/workspace/asdf/target/*jar s3://vasu2"
    }

Internet Gateway

public IP


Nat gateway

routing table-- route
subnet-- configuration


NAT Gateway

network-add vpc
subnet-- add public\private
dhcp- enable/disable



---------------------------------------------


PuvvulaM@HBADT4401133 MINGW64 ~/Downloads
$ ssh -i "awsnew.pem" ubuntu@ec2-18-224-228-96.us-east-2.compute.amazonaws.com
The authenticity of host 'ec2-18-224-228-96.us-east-2.compute.amazonaws.com (18.224.228.96)' can't be established.
ECDSA key fingerprint is SHA256:XZLkii8DqjUQAJZfp04Ty8laHzm0FvYy20OAFRSeZWY.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'ec2-18-224-228-96.us-east-2.compute.amazonaws.com,18.224.228.96' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-1065-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Jun 19 18:09:02 UTC 2020

  System load:  0.09              Processes:           110
  Usage of /:   13.8% of 7.69GB   Users logged in:     0
  Memory usage: 16%               IP address for ens5: 172.31.39.83
  Swap usage:   0%

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

ubuntu@ip-172-31-39-83:~$ sudo apt update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]
Get:4 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 Packages [8570 kB]
Get:5 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe Translation-en [4941 kB]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/multiverse amd64 Packages [151 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/multiverse Translation-en [108 kB]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 Packages [969 kB]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main Translation-en [329 kB]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/restricted amd64 Packages [60.5 kB]
Get:12 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/restricted Translation-en [14.7 kB]
Get:13 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 Packages [1085 kB]
Get:14 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe Translation-en [337 kB]
Get:15 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 Packages [15.9 kB]
Get:16 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/multiverse Translation-en [6420 B]
Get:17 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/main amd64 Packages [7516 B]
Get:18 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/main Translation-en [4764 B]
Get:19 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/universe amd64 Packages [7484 B]
Get:20 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/universe Translation-en [4436 B]
Get:21 http://security.ubuntu.com/ubuntu bionic-security/main amd64 Packages [748 kB]
Get:22 http://security.ubuntu.com/ubuntu bionic-security/main Translation-en [237 kB]
Get:23 http://security.ubuntu.com/ubuntu bionic-security/restricted amd64 Packages [50.8 kB]
Get:24 http://security.ubuntu.com/ubuntu bionic-security/restricted Translation-en [12.3 kB]
Get:25 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 Packages [673 kB]
Get:26 http://security.ubuntu.com/ubuntu bionic-security/universe Translation-en [223 kB]
Get:27 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 Packages [7808 B]
Get:28 http://security.ubuntu.com/ubuntu bionic-security/multiverse Translation-en [2856 B]
Fetched 18.8 MB in 4s (5266 kB/s)
Reading package lists... Done
Building dependency tree
Reading state information... Done
73 packages can be upgraded. Run 'apt list --upgradable' to see them.
ubuntu@ip-172-31-39-83:~$ java -version

Command 'java' not found, but can be installed with:

sudo apt install default-jre
sudo apt install openjdk-11-jre-headless
sudo apt install openjdk-8-jre-headless

ubuntu@ip-172-31-39-83:~$ sudo apt install openjdk-8-jre-headless
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  ca-certificates-java fontconfig-config fonts-dejavu-core java-common libavahi-client3 libavahi-common-data libavahi-common3 libcups2 libfontconfig1 libjpeg-turbo8 libjpeg8 liblcms2-2
  libnspr4 libnss3 libpcsclite1 libxi6 libxrender1 libxtst6 x11-common
Suggested packages:
  default-jre cups-common liblcms2-utils pcscd libnss-mdns fonts-dejavu-extra fonts-ipafont-gothic fonts-ipafont-mincho fonts-wqy-microhei fonts-wqy-zenhei fonts-indic
The following NEW packages will be installed:
  ca-certificates-java fontconfig-config fonts-dejavu-core java-common libavahi-client3 libavahi-common-data libavahi-common3 libcups2 libfontconfig1 libjpeg-turbo8 libjpeg8 liblcms2-2
  libnspr4 libnss3 libpcsclite1 libxi6 libxrender1 libxtst6 openjdk-8-jre-headless x11-common
0 upgraded, 20 newly installed, 0 to remove and 73 not upgraded.
Need to get 30.7 MB of archives.
After this operation, 111 MB of additional disk space will be used.
Do you want to continue? [Y/n] yes
Get:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libjpeg-turbo8 amd64 1.5.2-0ubuntu5.18.04.4 [110 kB]
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 java-common all 0.68ubuntu1~18.04.1 [14.5 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libavahi-common-data amd64 0.7-3.1ubuntu1.2 [22.1 kB]
Get:4 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libavahi-common3 amd64 0.7-3.1ubuntu1.2 [21.6 kB]
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libavahi-client3 amd64 0.7-3.1ubuntu1.2 [25.2 kB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libcups2 amd64 2.2.7-1ubuntu2.8 [211 kB]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 liblcms2-2 amd64 2.9-1ubuntu0.1 [139 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libjpeg8 amd64 8c-2ubuntu8 [2194 B]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 fonts-dejavu-core all 2.37-1 [1041 kB]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 fontconfig-config all 2.12.6-0ubuntu2 [55.8 kB]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libfontconfig1 amd64 2.12.6-0ubuntu2 [137 kB]
Get:12 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libnspr4 amd64 2:4.18-1ubuntu1 [112 kB]
Get:13 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libnss3 amd64 2:3.35-2ubuntu2.8 [1136 kB]
Get:14 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libpcsclite1 amd64 1.8.23-1 [21.3 kB]
Get:15 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxi6 amd64 2:1.7.9-1 [29.2 kB]
Get:16 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxrender1 amd64 1:0.9.10-1 [18.7 kB]
Get:17 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 x11-common all 1:7.7+19ubuntu7.1 [22.5 kB]
Get:18 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxtst6 amd64 2:1.2.3-1 [12.8 kB]
Get:19 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 openjdk-8-jre-headless amd64 8u252-b09-1~18.04 [27.5 MB]
Get:20 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 ca-certificates-java all 20180516ubuntu1~18.04.1 [12.2 kB]
Fetched 30.7 MB in 1s (51.7 MB/s)
Selecting previously unselected package libjpeg-turbo8:amd64.
(Reading database ... 56588 files and directories currently installed.)
Preparing to unpack .../00-libjpeg-turbo8_1.5.2-0ubuntu5.18.04.4_amd64.deb ...
Unpacking libjpeg-turbo8:amd64 (1.5.2-0ubuntu5.18.04.4) ...
Selecting previously unselected package java-common.
Preparing to unpack .../01-java-common_0.68ubuntu1~18.04.1_all.deb ...
Unpacking java-common (0.68ubuntu1~18.04.1) ...
Selecting previously unselected package libavahi-common-data:amd64.
Preparing to unpack .../02-libavahi-common-data_0.7-3.1ubuntu1.2_amd64.deb ...
Unpacking libavahi-common-data:amd64 (0.7-3.1ubuntu1.2) ...
Selecting previously unselected package libavahi-common3:amd64.
Preparing to unpack .../03-libavahi-common3_0.7-3.1ubuntu1.2_amd64.deb ...
Unpacking libavahi-common3:amd64 (0.7-3.1ubuntu1.2) ...
Selecting previously unselected package libavahi-client3:amd64.
Preparing to unpack .../04-libavahi-client3_0.7-3.1ubuntu1.2_amd64.deb ...
Unpacking libavahi-client3:amd64 (0.7-3.1ubuntu1.2) ...
Selecting previously unselected package libcups2:amd64.
Preparing to unpack .../05-libcups2_2.2.7-1ubuntu2.8_amd64.deb ...
Unpacking libcups2:amd64 (2.2.7-1ubuntu2.8) ...
Selecting previously unselected package liblcms2-2:amd64.
Preparing to unpack .../06-liblcms2-2_2.9-1ubuntu0.1_amd64.deb ...
Unpacking liblcms2-2:amd64 (2.9-1ubuntu0.1) ...
Selecting previously unselected package libjpeg8:amd64.
Preparing to unpack .../07-libjpeg8_8c-2ubuntu8_amd64.deb ...
Unpacking libjpeg8:amd64 (8c-2ubuntu8) ...
Selecting previously unselected package fonts-dejavu-core.
Preparing to unpack .../08-fonts-dejavu-core_2.37-1_all.deb ...
Unpacking fonts-dejavu-core (2.37-1) ...
Selecting previously unselected package fontconfig-config.
Preparing to unpack .../09-fontconfig-config_2.12.6-0ubuntu2_all.deb ...
Unpacking fontconfig-config (2.12.6-0ubuntu2) ...
Selecting previously unselected package libfontconfig1:amd64.
Preparing to unpack .../10-libfontconfig1_2.12.6-0ubuntu2_amd64.deb ...
Unpacking libfontconfig1:amd64 (2.12.6-0ubuntu2) ...
Selecting previously unselected package libnspr4:amd64.
Preparing to unpack .../11-libnspr4_2%3a4.18-1ubuntu1_amd64.deb ...
Unpacking libnspr4:amd64 (2:4.18-1ubuntu1) ...
Selecting previously unselected package libnss3:amd64.
Preparing to unpack .../12-libnss3_2%3a3.35-2ubuntu2.8_amd64.deb ...
Unpacking libnss3:amd64 (2:3.35-2ubuntu2.8) ...
Selecting previously unselected package libpcsclite1:amd64.
Preparing to unpack .../13-libpcsclite1_1.8.23-1_amd64.deb ...
Unpacking libpcsclite1:amd64 (1.8.23-1) ...
Selecting previously unselected package libxi6:amd64.
Preparing to unpack .../14-libxi6_2%3a1.7.9-1_amd64.deb ...
Unpacking libxi6:amd64 (2:1.7.9-1) ...
Selecting previously unselected package libxrender1:amd64.
Preparing to unpack .../15-libxrender1_1%3a0.9.10-1_amd64.deb ...
Unpacking libxrender1:amd64 (1:0.9.10-1) ...
Selecting previously unselected package x11-common.
Preparing to unpack .../16-x11-common_1%3a7.7+19ubuntu7.1_all.deb ...
dpkg-query: no packages found matching nux-tools
Unpacking x11-common (1:7.7+19ubuntu7.1) ...
Selecting previously unselected package libxtst6:amd64.
Preparing to unpack .../17-libxtst6_2%3a1.2.3-1_amd64.deb ...
Unpacking libxtst6:amd64 (2:1.2.3-1) ...
Selecting previously unselected package openjdk-8-jre-headless:amd64.
Preparing to unpack .../18-openjdk-8-jre-headless_8u252-b09-1~18.04_amd64.deb ...
Unpacking openjdk-8-jre-headless:amd64 (8u252-b09-1~18.04) ...
Selecting previously unselected package ca-certificates-java.
Preparing to unpack .../19-ca-certificates-java_20180516ubuntu1~18.04.1_all.deb ...
Unpacking ca-certificates-java (20180516ubuntu1~18.04.1) ...
Setting up libxi6:amd64 (2:1.7.9-1) ...
Setting up liblcms2-2:amd64 (2.9-1ubuntu0.1) ...
Setting up libpcsclite1:amd64 (1.8.23-1) ...
Setting up fonts-dejavu-core (2.37-1) ...
Setting up java-common (0.68ubuntu1~18.04.1) ...
Setting up libjpeg-turbo8:amd64 (1.5.2-0ubuntu5.18.04.4) ...
Setting up libnspr4:amd64 (2:4.18-1ubuntu1) ...
Setting up libxrender1:amd64 (1:0.9.10-1) ...
Setting up x11-common (1:7.7+19ubuntu7.1) ...
update-rc.d: warning: start and stop actions are no longer supported; falling back to defaults
Setting up libavahi-common-data:amd64 (0.7-3.1ubuntu1.2) ...
Setting up libjpeg8:amd64 (8c-2ubuntu8) ...
Setting up fontconfig-config (2.12.6-0ubuntu2) ...
Setting up libnss3:amd64 (2:3.35-2ubuntu2.8) ...
Setting up libxtst6:amd64 (2:1.2.3-1) ...
Setting up libavahi-common3:amd64 (0.7-3.1ubuntu1.2) ...
Setting up libfontconfig1:amd64 (2.12.6-0ubuntu2) ...
Setting up libavahi-client3:amd64 (0.7-3.1ubuntu1.2) ...
Setting up libcups2:amd64 (2.2.7-1ubuntu2.8) ...
Setting up ca-certificates-java (20180516ubuntu1~18.04.1) ...
head: cannot open '/etc/ssl/certs/java/cacerts' for reading: No such file or directory
Adding debian:OpenTrust_Root_CA_G2.pem
Adding debian:Starfield_Root_Certificate_Authority_-_G2.pem
Adding debian:GeoTrust_Universal_CA.pem
Adding debian:TrustCor_RootCert_CA-1.pem
Adding debian:T-TeleSec_GlobalRoot_Class_3.pem
Adding debian:TrustCor_ECA-1.pem
Adding debian:QuoVadis_Root_CA_1_G3.pem
Adding debian:Certigna.pem
Adding debian:Staat_der_Nederlanden_Root_CA_-_G2.pem
Adding debian:CA_Disig_Root_R2.pem
Adding debian:D-TRUST_Root_Class_3_CA_2_EV_2009.pem
Adding debian:Hellenic_Academic_and_Research_Institutions_RootCA_2015.pem
Adding debian:Visa_eCommerce_Root.pem
Adding debian:Comodo_AAA_Services_root.pem
Adding debian:Autoridad_de_Certificacion_Firmaprofesional_CIF_A62634068.pem
Adding debian:Actalis_Authentication_Root_CA.pem
Adding debian:DigiCert_Assured_ID_Root_G3.pem
Adding debian:Hongkong_Post_Root_CA_1.pem
Adding debian:thawte_Primary_Root_CA_-_G2.pem
Adding debian:Certum_Trusted_Network_CA_2.pem
Adding debian:Global_Chambersign_Root_-_2008.pem
Adding debian:DigiCert_Trusted_Root_G4.pem
Adding debian:DigiCert_Global_Root_G2.pem
Adding debian:Amazon_Root_CA_2.pem
Adding debian:TeliaSonera_Root_CA_v1.pem
Adding debian:QuoVadis_Root_CA_2.pem
Adding debian:Secure_Global_CA.pem
Adding debian:COMODO_RSA_Certification_Authority.pem
Adding debian:GDCA_TrustAUTH_R5_ROOT.pem
Adding debian:E-Tugra_Certification_Authority.pem
Adding debian:ACCVRAIZ1.pem
Adding debian:LuxTrust_Global_Root_2.pem
Adding debian:EE_Certification_Centre_Root_CA.pem
Adding debian:AffirmTrust_Networking.pem
Adding debian:Starfield_Class_2_CA.pem
Adding debian:Sonera_Class_2_Root_CA.pem
Adding debian:NetLock_Arany_=Class_Gold=_Főtanúsítvány.pem
Adding debian:GeoTrust_Global_CA.pem
Adding debian:XRamp_Global_CA_Root.pem
Adding debian:OpenTrust_Root_CA_G1.pem
Adding debian:Trustis_FPS_Root_CA.pem
Adding debian:COMODO_ECC_Certification_Authority.pem
Adding debian:GeoTrust_Primary_Certification_Authority_-_G3.pem
Adding debian:DigiCert_Global_Root_CA.pem
Adding debian:QuoVadis_Root_CA.pem
Adding debian:TWCA_Global_Root_CA.pem
Adding debian:ePKI_Root_Certification_Authority.pem
Adding debian:SwissSign_Silver_CA_-_G2.pem
Adding debian:Certum_Trusted_Network_CA.pem
Adding debian:Certplus_Root_CA_G1.pem
Adding debian:IdenTrust_Public_Sector_Root_CA_1.pem
Adding debian:DST_Root_CA_X3.pem
Adding debian:AffirmTrust_Commercial.pem
Adding debian:QuoVadis_Root_CA_2_G3.pem
Adding debian:OpenTrust_Root_CA_G3.pem
Adding debian:TrustCor_RootCert_CA-2.pem
Adding debian:Certplus_Class_2_Primary_CA.pem
Adding debian:CFCA_EV_ROOT.pem
Adding debian:Hellenic_Academic_and_Research_Institutions_RootCA_2011.pem
Adding debian:USERTrust_RSA_Certification_Authority.pem
Adding debian:Verisign_Class_3_Public_Primary_Certification_Authority_-_G3.pem
Adding debian:Amazon_Root_CA_1.pem
Adding debian:Entrust.net_Premium_2048_Secure_Server_CA.pem
Adding debian:Certinomis_-_Root_CA.pem
Adding debian:AddTrust_External_Root.pem
Adding debian:GlobalSign_ECC_Root_CA_-_R4.pem
Adding debian:TWCA_Root_Certification_Authority.pem
Adding debian:SSL.com_Root_Certification_Authority_RSA.pem
Adding debian:certSIGN_ROOT_CA.pem
Adding debian:QuoVadis_Root_CA_3.pem
Adding debian:QuoVadis_Root_CA_3_G3.pem
Adding debian:Microsec_e-Szigno_Root_CA_2009.pem
Adding debian:SSL.com_Root_Certification_Authority_ECC.pem
Adding debian:Go_Daddy_Root_Certificate_Authority_-_G2.pem
Adding debian:Buypass_Class_2_Root_CA.pem
Adding debian:DigiCert_Global_Root_G3.pem
Adding debian:Starfield_Services_Root_Certificate_Authority_-_G2.pem
Adding debian:Deutsche_Telekom_Root_CA_2.pem
Adding debian:ISRG_Root_X1.pem
Adding debian:Cybertrust_Global_Root.pem
Adding debian:AC_RAIZ_FNMT-RCM.pem
Adding debian:DigiCert_High_Assurance_EV_Root_CA.pem
Adding debian:SecureSign_RootCA11.pem
Adding debian:TÜRKTRUST_Elektronik_Sertifika_Hizmet_Sağlayıcısı_H5.pem
Adding debian:GeoTrust_Universal_CA_2.pem
Adding debian:TUBITAK_Kamu_SM_SSL_Kok_Sertifikasi_-_Surum_1.pem
Adding debian:Security_Communication_Root_CA.pem
Adding debian:AffirmTrust_Premium.pem
Adding debian:VeriSign_Universal_Root_Certification_Authority.pem
Adding debian:VeriSign_Class_3_Public_Primary_Certification_Authority_-_G5.pem
Adding debian:GlobalSign_ECC_Root_CA_-_R5.pem
Adding debian:Entrust_Root_Certification_Authority.pem
Adding debian:GeoTrust_Primary_Certification_Authority.pem
Adding debian:Go_Daddy_Class_2_CA.pem
Adding debian:COMODO_Certification_Authority.pem
Adding debian:GlobalSign_Root_CA_-_R2.pem
Adding debian:SwissSign_Gold_CA_-_G2.pem
Adding debian:D-TRUST_Root_Class_3_CA_2_2009.pem
Adding debian:VeriSign_Class_3_Public_Primary_Certification_Authority_-_G4.pem
Adding debian:GeoTrust_Primary_Certification_Authority_-_G2.pem
Adding debian:Entrust_Root_Certification_Authority_-_EC1.pem
Adding debian:thawte_Primary_Root_CA.pem
Adding debian:Security_Communication_RootCA2.pem
Adding debian:Certplus_Root_CA_G2.pem
Adding debian:Chambers_of_Commerce_Root_-_2008.pem
Adding debian:Entrust_Root_Certification_Authority_-_G2.pem
Adding debian:Taiwan_GRCA.pem
Adding debian:Hellenic_Academic_and_Research_Institutions_ECC_RootCA_2015.pem
Adding debian:DigiCert_Assured_ID_Root_G2.pem
Adding debian:Baltimore_CyberTrust_Root.pem
Adding debian:Network_Solutions_Certificate_Authority.pem
Adding debian:GlobalSign_Root_CA_-_R3.pem
Adding debian:IdenTrust_Commercial_Root_CA_1.pem
Adding debian:SSL.com_EV_Root_Certification_Authority_ECC.pem
Adding debian:Amazon_Root_CA_4.pem
Adding debian:GlobalSign_Root_CA.pem
Adding debian:thawte_Primary_Root_CA_-_G3.pem
Adding debian:Atos_TrustedRoot_2011.pem
Adding debian:Staat_der_Nederlanden_Root_CA_-_G3.pem
Adding debian:SecureTrust_CA.pem
Adding debian:Staat_der_Nederlanden_EV_Root_CA.pem
Adding debian:SZAFIR_ROOT_CA2.pem
Adding debian:DigiCert_Assured_ID_Root_CA.pem
Adding debian:Buypass_Class_3_Root_CA.pem
Adding debian:USERTrust_ECC_Certification_Authority.pem
Adding debian:T-TeleSec_GlobalRoot_Class_2.pem
Adding debian:Amazon_Root_CA_3.pem
Adding debian:EC-ACC.pem
Adding debian:SSL.com_EV_Root_Certification_Authority_RSA_R2.pem
Adding debian:AffirmTrust_Premium_ECC.pem
Adding debian:OISTE_WISeKey_Global_Root_GB_CA.pem
Adding debian:Izenpe.com.pem
Adding debian:OISTE_WISeKey_Global_Root_GA_CA.pem
done.
Processing triggers for ureadahead (0.100.0-21) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Processing triggers for systemd (237-3ubuntu10.39) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for ca-certificates (20180409) ...
Updating certificates in /etc/ssl/certs...
0 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...

done.
done.
Setting up openjdk-8-jre-headless:amd64 (8u252-b09-1~18.04) ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/rmid to provide /usr/bin/rmid (rmid) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java to provide /usr/bin/java (java) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/keytool to provide /usr/bin/keytool (keytool) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/jjs to provide /usr/bin/jjs (jjs) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/pack200 to provide /usr/bin/pack200 (pack200) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/rmiregistry to provide /usr/bin/rmiregistry (rmiregistry) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/unpack200 to provide /usr/bin/unpack200 (unpack200) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/orbd to provide /usr/bin/orbd (orbd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/servertool to provide /usr/bin/servertool (servertool) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/tnameserv to provide /usr/bin/tnameserv (tnameserv) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/jexec to provide /usr/bin/jexec (jexec) in auto mode
ubuntu@ip-172-31-39-83:~$ java -version
openjdk version "1.8.0_252"
OpenJDK Runtime Environment (build 1.8.0_252-8u252-b09-1~18.04-b09)
OpenJDK 64-Bit Server VM (build 25.252-b09, mixed mode)
ubuntu@ip-172-31-39-83:~$ sudo add-apt-repository ppa:openjdk-r/ppa

 More info: https://launchpad.net/~openjdk-r/+archive/ubuntu/ppa
Press [ENTER] to continue or Ctrl-c to cancel adding it.

Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:4 http://security.ubuntu.com/ubuntu bionic-security InRelease
Get:5 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic InRelease [15.4 kB]
Get:6 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic/main amd64 Packages [9372 B]
Get:7 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic/main Translation-en [1360 B]
Fetched 26.1 kB in 1s (29.7 kB/s)
Reading package lists... Done
ubuntu@ip-172-31-39-83:~$ sudo apt-get update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:4 http://security.ubuntu.com/ubuntu bionic-security InRelease
Hit:5 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic InRelease
Reading package lists... Done
ubuntu@ip-172-31-39-83:~$ sudo apt-get install openjdk-8-jdk
sudo: apt-getinstall: command not found
ubuntu@ip-172-31-39-83:~$ sudo apt-get install openjdk-8-jdk
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  adwaita-icon-theme at-spi2-core fontconfig fonts-dejavu-extra gtk-update-icon-cache hicolor-icon-theme humanity-icon-theme libasound2 libasound2-data libasyncns0 libatk-bridge2.0-0
  libatk-wrapper-java libatk-wrapper-java-jni libatk1.0-0 libatk1.0-data libatspi2.0-0 libcairo2 libcroco3 libdatrie1 libdrm-amdgpu1 libdrm-common libdrm-intel1 libdrm-nouveau2
  libdrm-radeon1 libdrm2 libflac8 libfontenc1 libgail-common libgail18 libgdk-pixbuf2.0-0 libgdk-pixbuf2.0-bin libgdk-pixbuf2.0-common libgif7 libgl1 libgl1-mesa-dri libgl1-mesa-glx
  libglapi-mesa libglvnd0 libglx-mesa0 libglx0 libgraphite2-3 libgtk2.0-0 libgtk2.0-bin libgtk2.0-common libharfbuzz0b libice-dev libice6 libjbig0 libllvm9 libogg0 libpango-1.0-0
  libpangocairo-1.0-0 libpangoft2-1.0-0 libpciaccess0 libpixman-1-0 libpthread-stubs0-dev libpulse0 librsvg2-2 librsvg2-common libsensors4 libsm-dev libsm6 libsndfile1 libthai-data libthai0
  libtiff5 libvorbis0a libvorbisenc2 libx11-dev libx11-doc libx11-xcb1 libxau-dev libxaw7 libxcb-dri2-0 libxcb-dri3-0 libxcb-glx0 libxcb-present0 libxcb-render0 libxcb-shape0 libxcb-shm0
  libxcb-sync1 libxcb1-dev libxcomposite1 libxcursor1 libxdamage1 libxdmcp-dev libxfixes3 libxft2 libxinerama1 libxmu6 libxpm4 libxrandr2 libxshmfence1 libxt-dev libxt6 libxv1 libxxf86dga1
  libxxf86vm1 openjdk-8-jdk-headless openjdk-8-jre ubuntu-mono x11-utils x11proto-core-dev x11proto-dev xorg-sgml-doctools xtrans-dev
Suggested packages:
  libasound2-plugins alsa-utils gvfs libice-doc pulseaudio librsvg2-bin lm-sensors libsm-doc libxcb-doc libxt-doc openjdk-8-demo openjdk-8-source visualvm icedtea-8-plugin mesa-utils
The following NEW packages will be installed:
  adwaita-icon-theme at-spi2-core fontconfig fonts-dejavu-extra gtk-update-icon-cache hicolor-icon-theme humanity-icon-theme libasound2 libasound2-data libasyncns0 libatk-bridge2.0-0
  libatk-wrapper-java libatk-wrapper-java-jni libatk1.0-0 libatk1.0-data libatspi2.0-0 libcairo2 libcroco3 libdatrie1 libdrm-amdgpu1 libdrm-intel1 libdrm-nouveau2 libdrm-radeon1 libflac8
  libfontenc1 libgail-common libgail18 libgdk-pixbuf2.0-0 libgdk-pixbuf2.0-bin libgdk-pixbuf2.0-common libgif7 libgl1 libgl1-mesa-dri libgl1-mesa-glx libglapi-mesa libglvnd0 libglx-mesa0
  libglx0 libgraphite2-3 libgtk2.0-0 libgtk2.0-bin libgtk2.0-common libharfbuzz0b libice-dev libice6 libjbig0 libllvm9 libogg0 libpango-1.0-0 libpangocairo-1.0-0 libpangoft2-1.0-0
  libpciaccess0 libpixman-1-0 libpthread-stubs0-dev libpulse0 librsvg2-2 librsvg2-common libsensors4 libsm-dev libsm6 libsndfile1 libthai-data libthai0 libtiff5 libvorbis0a libvorbisenc2
  libx11-dev libx11-doc libx11-xcb1 libxau-dev libxaw7 libxcb-dri2-0 libxcb-dri3-0 libxcb-glx0 libxcb-present0 libxcb-render0 libxcb-shape0 libxcb-shm0 libxcb-sync1 libxcb1-dev
  libxcomposite1 libxcursor1 libxdamage1 libxdmcp-dev libxfixes3 libxft2 libxinerama1 libxmu6 libxpm4 libxrandr2 libxshmfence1 libxt-dev libxt6 libxv1 libxxf86dga1 libxxf86vm1 openjdk-8-jdk
  openjdk-8-jdk-headless openjdk-8-jre ubuntu-mono x11-utils x11proto-core-dev x11proto-dev xorg-sgml-doctools xtrans-dev
The following packages will be upgraded:
  libdrm-common libdrm2
2 upgraded, 105 newly installed, 0 to remove and 71 not upgraded.
Need to get 51.1 MB of archives.
After this operation, 433 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 fontconfig amd64 2.12.6-0ubuntu2 [169 kB]
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libogg0 amd64 1.3.2-1 [17.2 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libice6 amd64 2:1.0.9-2 [40.2 kB]
Get:4 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libsm6 amd64 2:1.2.2-1 [15.8 kB]
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxft2 amd64 2.3.2-1 [36.1 kB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxinerama1 amd64 2:1.1.3-1 [7908 B]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxxf86dga1 amd64 2:1.1.4-1 [13.7 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxxf86vm1 amd64 1:1.1.4-1 [10.6 kB]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-common all 2.4.101-2~18.04.1 [5560 B]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm2 amd64 2.4.101-2~18.04.1 [32.3 kB]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 hicolor-icon-theme all 0.17-2 [9976 B]
Get:12 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libjbig0 amd64 2.1-3.1build1 [26.7 kB]
Get:13 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libtiff5 amd64 4.0.9-5ubuntu0.3 [153 kB]
Get:14 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgdk-pixbuf2.0-common all 2.36.11-2 [4536 B]
Get:15 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgdk-pixbuf2.0-0 amd64 2.36.11-2 [165 kB]
Get:16 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 gtk-update-icon-cache amd64 3.22.30-1ubuntu4 [28.3 kB]
Get:17 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libpixman-1-0 amd64 0.34.0-2 [229 kB]
Get:18 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-render0 amd64 1.13-2~ubuntu18.04 [14.7 kB]
Get:19 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-shm0 amd64 1.13-2~ubuntu18.04 [5600 B]
Get:20 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libcairo2 amd64 1.15.10-2ubuntu0.1 [580 kB]
Get:21 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libcroco3 amd64 0.6.12-2 [81.3 kB]
Get:22 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libthai-data all 0.1.27-2 [133 kB]
Get:23 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libdatrie1 amd64 0.2.10-7 [17.8 kB]
Get:24 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libthai0 amd64 0.1.27-2 [18.0 kB]
Get:25 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libpango-1.0-0 amd64 1.40.14-1ubuntu0.1 [153 kB]
Get:26 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgraphite2-3 amd64 1.3.11-2 [78.7 kB]
Get:27 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libharfbuzz0b amd64 1.7.2-1ubuntu1 [232 kB]
Get:28 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libpangoft2-1.0-0 amd64 1.40.14-1ubuntu0.1 [33.2 kB]
Get:29 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libpangocairo-1.0-0 amd64 1.40.14-1ubuntu0.1 [20.8 kB]
Get:30 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 librsvg2-2 amd64 2.40.20-2 [98.6 kB]
Get:31 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 librsvg2-common amd64 2.40.20-2 [5124 B]
Get:32 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 humanity-icon-theme all 0.6.15 [1250 kB]
Get:33 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 ubuntu-mono all 16.10+18.04.20181005-0ubuntu1 [149 kB]
Get:34 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 adwaita-icon-theme all 3.28.0-1ubuntu1 [3306 kB]
Get:35 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatspi2.0-0 amd64 2.28.0-1 [59.6 kB]
Get:36 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 at-spi2-core amd64 2.28.0-1 [47.9 kB]
Get:37 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 fonts-dejavu-extra all 2.37-1 [1953 kB]
Get:38 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libasound2-data all 1.1.3-5ubuntu0.5 [38.7 kB]
Get:39 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libasound2 amd64 1.1.3-5ubuntu0.5 [360 kB]
Get:40 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libasyncns0 amd64 0.8-6 [12.1 kB]
Get:41 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk1.0-data all 2.28.1-1 [2992 B]
Get:42 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk1.0-0 amd64 2.28.1-1 [43.9 kB]
Get:43 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk-bridge2.0-0 amd64 2.26.2-1 [57.3 kB]
Get:44 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libfontenc1 amd64 1:1.1.3-1 [13.9 kB]
Get:45 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libglvnd0 amd64 1.0.0-2ubuntu2.3 [47.0 kB]
Get:46 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libglapi-mesa amd64 19.2.8-0ubuntu0~18.04.3 [26.5 kB]
Get:47 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libx11-xcb1 amd64 2:1.6.4-3ubuntu0.2 [9376 B]
Get:48 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-dri2-0 amd64 1.13-2~ubuntu18.04 [6920 B]
Get:49 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-dri3-0 amd64 1.13-2~ubuntu18.04 [6568 B]
Get:50 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-glx0 amd64 1.13-2~ubuntu18.04 [22.1 kB]
Get:51 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-present0 amd64 1.13-2~ubuntu18.04 [5552 B]
Get:52 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-sync1 amd64 1.13-2~ubuntu18.04 [8808 B]
Get:53 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxdamage1 amd64 1:1.1.4-3 [6934 B]
Get:54 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxfixes3 amd64 1:5.0.3-1 [10.8 kB]
Get:55 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxshmfence1 amd64 1.3-1 [5028 B]
Get:56 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-amdgpu1 amd64 2.4.101-2~18.04.1 [18.2 kB]
Get:57 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libpciaccess0 amd64 0.14-1 [17.9 kB]
Get:58 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-intel1 amd64 2.4.101-2~18.04.1 [60.0 kB]
Get:59 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-nouveau2 amd64 2.4.101-2~18.04.1 [16.5 kB]
Get:60 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-radeon1 amd64 2.4.101-2~18.04.1 [21.7 kB]
Get:61 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libllvm9 amd64 1:9-2~ubuntu18.04.2 [14.8 MB]
Get:62 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libsensors4 amd64 1:3.4.0-4 [28.8 kB]
Get:63 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgl1-mesa-dri amd64 19.2.8-0ubuntu0~18.04.3 [8811 kB]
Get:64 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libglx-mesa0 amd64 19.2.8-0ubuntu0~18.04.3 [139 kB]
Get:65 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libglx0 amd64 1.0.0-2ubuntu2.3 [28.1 kB]
Get:66 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgl1 amd64 1.0.0-2ubuntu2.3 [86.2 kB]
Get:67 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgl1-mesa-glx amd64 19.2.8-0ubuntu0~18.04.3 [5528 B]
Get:68 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxt6 amd64 1:1.1.5-1 [160 kB]
Get:69 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxmu6 amd64 2:1.1.2-2 [46.0 kB]
Get:70 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxpm4 amd64 1:3.5.12-1 [34.0 kB]
Get:71 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxaw7 amd64 2:1.0.13-1 [173 kB]
Get:72 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-shape0 amd64 1.13-2~ubuntu18.04 [5972 B]
Get:73 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxcomposite1 amd64 1:0.4.4-2 [6988 B]
Get:74 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxrandr2 amd64 2:1.5.1-1 [18.1 kB]
Get:75 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxv1 amd64 2:1.0.11-1 [10.7 kB]
Get:76 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 x11-utils amd64 7.7+3build1 [196 kB]
Get:77 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk-wrapper-java all 0.33.3-20ubuntu0.1 [34.7 kB]
Get:78 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk-wrapper-java-jni amd64 0.33.3-20ubuntu0.1 [28.3 kB]
Get:79 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libflac8 amd64 1.3.2-1 [213 kB]
Get:80 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgtk2.0-common all 2.24.32-1ubuntu1 [125 kB]
Get:81 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxcursor1 amd64 1:1.1.15-1 [19.8 kB]
Get:82 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgtk2.0-0 amd64 2.24.32-1ubuntu1 [1769 kB]
Get:83 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgail18 amd64 2.24.32-1ubuntu1 [14.2 kB]
Get:84 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgail-common amd64 2.24.32-1ubuntu1 [112 kB]
Get:85 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgdk-pixbuf2.0-bin amd64 2.36.11-2 [7864 B]
Get:86 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgif7 amd64 5.1.4-2ubuntu0.1 [30.9 kB]
Get:87 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgtk2.0-bin amd64 2.24.32-1ubuntu1 [7536 B]
Get:88 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 xorg-sgml-doctools all 1:1.11-1 [12.9 kB]
Get:89 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 x11proto-dev all 2018.4-4 [251 kB]
Get:90 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 x11proto-core-dev all 2018.4-4 [2620 B]
Get:91 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libice-dev amd64 2:1.0.9-2 [46.8 kB]
Get:92 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libpthread-stubs0-dev amd64 0.3-4 [4068 B]
Get:93 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libvorbis0a amd64 1.3.5-4.2 [86.4 kB]
Get:94 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libvorbisenc2 amd64 1.3.5-4.2 [70.7 kB]
Get:95 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libsndfile1 amd64 1.0.28-4ubuntu0.18.04.1 [170 kB]
Get:96 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libpulse0 amd64 1:11.1-1ubuntu7.8 [266 kB]
Get:97 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libsm-dev amd64 2:1.2.2-1 [16.2 kB]
Get:98 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxau-dev amd64 1:1.0.8-1 [11.1 kB]
Get:99 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxdmcp-dev amd64 1:1.1.2-3 [25.1 kB]
Get:100 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 xtrans-dev all 1.3.5-1 [70.5 kB]
Get:101 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb1-dev amd64 1.13-2~ubuntu18.04 [80.0 kB]
Get:102 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libx11-dev amd64 2:1.6.4-3ubuntu0.2 [640 kB]
Get:103 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libx11-doc all 2:1.6.4-3ubuntu0.2 [2065 kB]
Get:104 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxt-dev amd64 1:1.1.5-1 [395 kB]
Get:105 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 openjdk-8-jre amd64 8u252-b09-1~18.04 [69.8 kB]
Get:106 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 openjdk-8-jdk-headless amd64 8u252-b09-1~18.04 [8250 kB]
Get:107 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 openjdk-8-jdk amd64 8u252-b09-1~18.04 [1622 kB]
Fetched 51.1 MB in 2s (23.2 MB/s)
Extracting templates from packages: 100%
Selecting previously unselected package fontconfig.
(Reading database ... 57076 files and directories currently installed.)
Preparing to unpack .../000-fontconfig_2.12.6-0ubuntu2_amd64.deb ...
Unpacking fontconfig (2.12.6-0ubuntu2) ...
Selecting previously unselected package libogg0:amd64.
Preparing to unpack .../001-libogg0_1.3.2-1_amd64.deb ...
Unpacking libogg0:amd64 (1.3.2-1) ...
Selecting previously unselected package libice6:amd64.
Preparing to unpack .../002-libice6_2%3a1.0.9-2_amd64.deb ...
Unpacking libice6:amd64 (2:1.0.9-2) ...
Selecting previously unselected package libsm6:amd64.
Preparing to unpack .../003-libsm6_2%3a1.2.2-1_amd64.deb ...
Unpacking libsm6:amd64 (2:1.2.2-1) ...
Selecting previously unselected package libxft2:amd64.
Preparing to unpack .../004-libxft2_2.3.2-1_amd64.deb ...
Unpacking libxft2:amd64 (2.3.2-1) ...
Selecting previously unselected package libxinerama1:amd64.
Preparing to unpack .../005-libxinerama1_2%3a1.1.3-1_amd64.deb ...
Unpacking libxinerama1:amd64 (2:1.1.3-1) ...
Selecting previously unselected package libxxf86dga1:amd64.
Preparing to unpack .../006-libxxf86dga1_2%3a1.1.4-1_amd64.deb ...
Unpacking libxxf86dga1:amd64 (2:1.1.4-1) ...
Selecting previously unselected package libxxf86vm1:amd64.
Preparing to unpack .../007-libxxf86vm1_1%3a1.1.4-1_amd64.deb ...
Unpacking libxxf86vm1:amd64 (1:1.1.4-1) ...
Preparing to unpack .../008-libdrm-common_2.4.101-2~18.04.1_all.deb ...
Unpacking libdrm-common (2.4.101-2~18.04.1) over (2.4.99-1ubuntu1~18.04.2) ...
Preparing to unpack .../009-libdrm2_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm2:amd64 (2.4.101-2~18.04.1) over (2.4.99-1ubuntu1~18.04.2) ...
Selecting previously unselected package hicolor-icon-theme.
Preparing to unpack .../010-hicolor-icon-theme_0.17-2_all.deb ...
Unpacking hicolor-icon-theme (0.17-2) ...
Selecting previously unselected package libjbig0:amd64.
Preparing to unpack .../011-libjbig0_2.1-3.1build1_amd64.deb ...
Unpacking libjbig0:amd64 (2.1-3.1build1) ...
Selecting previously unselected package libtiff5:amd64.
Preparing to unpack .../012-libtiff5_4.0.9-5ubuntu0.3_amd64.deb ...
Unpacking libtiff5:amd64 (4.0.9-5ubuntu0.3) ...
Selecting previously unselected package libgdk-pixbuf2.0-common.
Preparing to unpack .../013-libgdk-pixbuf2.0-common_2.36.11-2_all.deb ...
Unpacking libgdk-pixbuf2.0-common (2.36.11-2) ...
Selecting previously unselected package libgdk-pixbuf2.0-0:amd64.
Preparing to unpack .../014-libgdk-pixbuf2.0-0_2.36.11-2_amd64.deb ...
Unpacking libgdk-pixbuf2.0-0:amd64 (2.36.11-2) ...
Selecting previously unselected package gtk-update-icon-cache.
Preparing to unpack .../015-gtk-update-icon-cache_3.22.30-1ubuntu4_amd64.deb ...
No diversion 'diversion of /usr/sbin/update-icon-caches to /usr/sbin/update-icon-caches.gtk2 by libgtk-3-bin', none removed.
No diversion 'diversion of /usr/share/man/man8/update-icon-caches.8.gz to /usr/share/man/man8/update-icon-caches.gtk2.8.gz by libgtk-3-bin', none removed.
Unpacking gtk-update-icon-cache (3.22.30-1ubuntu4) ...
Selecting previously unselected package libpixman-1-0:amd64.
Preparing to unpack .../016-libpixman-1-0_0.34.0-2_amd64.deb ...
Unpacking libpixman-1-0:amd64 (0.34.0-2) ...
Selecting previously unselected package libxcb-render0:amd64.
Preparing to unpack .../017-libxcb-render0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-render0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-shm0:amd64.
Preparing to unpack .../018-libxcb-shm0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-shm0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libcairo2:amd64.
Preparing to unpack .../019-libcairo2_1.15.10-2ubuntu0.1_amd64.deb ...
Unpacking libcairo2:amd64 (1.15.10-2ubuntu0.1) ...
Selecting previously unselected package libcroco3:amd64.
Preparing to unpack .../020-libcroco3_0.6.12-2_amd64.deb ...
Unpacking libcroco3:amd64 (0.6.12-2) ...
Selecting previously unselected package libthai-data.
Preparing to unpack .../021-libthai-data_0.1.27-2_all.deb ...
Unpacking libthai-data (0.1.27-2) ...
Selecting previously unselected package libdatrie1:amd64.
Preparing to unpack .../022-libdatrie1_0.2.10-7_amd64.deb ...
Unpacking libdatrie1:amd64 (0.2.10-7) ...
Selecting previously unselected package libthai0:amd64.
Preparing to unpack .../023-libthai0_0.1.27-2_amd64.deb ...
Unpacking libthai0:amd64 (0.1.27-2) ...
Selecting previously unselected package libpango-1.0-0:amd64.
Preparing to unpack .../024-libpango-1.0-0_1.40.14-1ubuntu0.1_amd64.deb ...
Unpacking libpango-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Selecting previously unselected package libgraphite2-3:amd64.
Preparing to unpack .../025-libgraphite2-3_1.3.11-2_amd64.deb ...
Unpacking libgraphite2-3:amd64 (1.3.11-2) ...
Selecting previously unselected package libharfbuzz0b:amd64.
Preparing to unpack .../026-libharfbuzz0b_1.7.2-1ubuntu1_amd64.deb ...
Unpacking libharfbuzz0b:amd64 (1.7.2-1ubuntu1) ...
Selecting previously unselected package libpangoft2-1.0-0:amd64.
Preparing to unpack .../027-libpangoft2-1.0-0_1.40.14-1ubuntu0.1_amd64.deb ...
Unpacking libpangoft2-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Selecting previously unselected package libpangocairo-1.0-0:amd64.
Preparing to unpack .../028-libpangocairo-1.0-0_1.40.14-1ubuntu0.1_amd64.deb ...
Unpacking libpangocairo-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Selecting previously unselected package librsvg2-2:amd64.
Preparing to unpack .../029-librsvg2-2_2.40.20-2_amd64.deb ...
Unpacking librsvg2-2:amd64 (2.40.20-2) ...
Selecting previously unselected package librsvg2-common:amd64.
Preparing to unpack .../030-librsvg2-common_2.40.20-2_amd64.deb ...
Unpacking librsvg2-common:amd64 (2.40.20-2) ...
Selecting previously unselected package humanity-icon-theme.
Preparing to unpack .../031-humanity-icon-theme_0.6.15_all.deb ...
Unpacking humanity-icon-theme (0.6.15) ...
Selecting previously unselected package ubuntu-mono.
Preparing to unpack .../032-ubuntu-mono_16.10+18.04.20181005-0ubuntu1_all.deb ...
Unpacking ubuntu-mono (16.10+18.04.20181005-0ubuntu1) ...
Selecting previously unselected package adwaita-icon-theme.
Preparing to unpack .../033-adwaita-icon-theme_3.28.0-1ubuntu1_all.deb ...
Unpacking adwaita-icon-theme (3.28.0-1ubuntu1) ...
Selecting previously unselected package libatspi2.0-0:amd64.
Preparing to unpack .../034-libatspi2.0-0_2.28.0-1_amd64.deb ...
Unpacking libatspi2.0-0:amd64 (2.28.0-1) ...
Selecting previously unselected package at-spi2-core.
Preparing to unpack .../035-at-spi2-core_2.28.0-1_amd64.deb ...
Unpacking at-spi2-core (2.28.0-1) ...
Selecting previously unselected package fonts-dejavu-extra.
Preparing to unpack .../036-fonts-dejavu-extra_2.37-1_all.deb ...
Unpacking fonts-dejavu-extra (2.37-1) ...
Selecting previously unselected package libasound2-data.
Preparing to unpack .../037-libasound2-data_1.1.3-5ubuntu0.5_all.deb ...
Unpacking libasound2-data (1.1.3-5ubuntu0.5) ...
Selecting previously unselected package libasound2:amd64.
Preparing to unpack .../038-libasound2_1.1.3-5ubuntu0.5_amd64.deb ...
Unpacking libasound2:amd64 (1.1.3-5ubuntu0.5) ...
Selecting previously unselected package libasyncns0:amd64.
Preparing to unpack .../039-libasyncns0_0.8-6_amd64.deb ...
Unpacking libasyncns0:amd64 (0.8-6) ...
Selecting previously unselected package libatk1.0-data.
Preparing to unpack .../040-libatk1.0-data_2.28.1-1_all.deb ...
Unpacking libatk1.0-data (2.28.1-1) ...
Selecting previously unselected package libatk1.0-0:amd64.
Preparing to unpack .../041-libatk1.0-0_2.28.1-1_amd64.deb ...
Unpacking libatk1.0-0:amd64 (2.28.1-1) ...
Selecting previously unselected package libatk-bridge2.0-0:amd64.
Preparing to unpack .../042-libatk-bridge2.0-0_2.26.2-1_amd64.deb ...
Unpacking libatk-bridge2.0-0:amd64 (2.26.2-1) ...
Selecting previously unselected package libfontenc1:amd64.
Preparing to unpack .../043-libfontenc1_1%3a1.1.3-1_amd64.deb ...
Unpacking libfontenc1:amd64 (1:1.1.3-1) ...
Selecting previously unselected package libglvnd0:amd64.
Preparing to unpack .../044-libglvnd0_1.0.0-2ubuntu2.3_amd64.deb ...
Unpacking libglvnd0:amd64 (1.0.0-2ubuntu2.3) ...
Selecting previously unselected package libglapi-mesa:amd64.
Preparing to unpack .../045-libglapi-mesa_19.2.8-0ubuntu0~18.04.3_amd64.deb ...
Unpacking libglapi-mesa:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Selecting previously unselected package libx11-xcb1:amd64.
Preparing to unpack .../046-libx11-xcb1_2%3a1.6.4-3ubuntu0.2_amd64.deb ...
Unpacking libx11-xcb1:amd64 (2:1.6.4-3ubuntu0.2) ...
Selecting previously unselected package libxcb-dri2-0:amd64.
Preparing to unpack .../047-libxcb-dri2-0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-dri2-0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-dri3-0:amd64.
Preparing to unpack .../048-libxcb-dri3-0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-dri3-0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-glx0:amd64.
Preparing to unpack .../049-libxcb-glx0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-glx0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-present0:amd64.
Preparing to unpack .../050-libxcb-present0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-present0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-sync1:amd64.
Preparing to unpack .../051-libxcb-sync1_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-sync1:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxdamage1:amd64.
Preparing to unpack .../052-libxdamage1_1%3a1.1.4-3_amd64.deb ...
Unpacking libxdamage1:amd64 (1:1.1.4-3) ...
Selecting previously unselected package libxfixes3:amd64.
Preparing to unpack .../053-libxfixes3_1%3a5.0.3-1_amd64.deb ...
Unpacking libxfixes3:amd64 (1:5.0.3-1) ...
Selecting previously unselected package libxshmfence1:amd64.
Preparing to unpack .../054-libxshmfence1_1.3-1_amd64.deb ...
Unpacking libxshmfence1:amd64 (1.3-1) ...
Selecting previously unselected package libdrm-amdgpu1:amd64.
Preparing to unpack .../055-libdrm-amdgpu1_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm-amdgpu1:amd64 (2.4.101-2~18.04.1) ...
Selecting previously unselected package libpciaccess0:amd64.
Preparing to unpack .../056-libpciaccess0_0.14-1_amd64.deb ...
Unpacking libpciaccess0:amd64 (0.14-1) ...
Selecting previously unselected package libdrm-intel1:amd64.
Preparing to unpack .../057-libdrm-intel1_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm-intel1:amd64 (2.4.101-2~18.04.1) ...
Selecting previously unselected package libdrm-nouveau2:amd64.
Preparing to unpack .../058-libdrm-nouveau2_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm-nouveau2:amd64 (2.4.101-2~18.04.1) ...
Selecting previously unselected package libdrm-radeon1:amd64.
Preparing to unpack .../059-libdrm-radeon1_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm-radeon1:amd64 (2.4.101-2~18.04.1) ...
Selecting previously unselected package libllvm9:amd64.
Preparing to unpack .../060-libllvm9_1%3a9-2~ubuntu18.04.2_amd64.deb ...
Unpacking libllvm9:amd64 (1:9-2~ubuntu18.04.2) ...
Selecting previously unselected package libsensors4:amd64.
Preparing to unpack .../061-libsensors4_1%3a3.4.0-4_amd64.deb ...
Unpacking libsensors4:amd64 (1:3.4.0-4) ...
Selecting previously unselected package libgl1-mesa-dri:amd64.
Preparing to unpack .../062-libgl1-mesa-dri_19.2.8-0ubuntu0~18.04.3_amd64.deb ...
Unpacking libgl1-mesa-dri:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Selecting previously unselected package libglx-mesa0:amd64.
Preparing to unpack .../063-libglx-mesa0_19.2.8-0ubuntu0~18.04.3_amd64.deb ...
Unpacking libglx-mesa0:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Selecting previously unselected package libglx0:amd64.
Preparing to unpack .../064-libglx0_1.0.0-2ubuntu2.3_amd64.deb ...
Unpacking libglx0:amd64 (1.0.0-2ubuntu2.3) ...
Selecting previously unselected package libgl1:amd64.
Preparing to unpack .../065-libgl1_1.0.0-2ubuntu2.3_amd64.deb ...
Unpacking libgl1:amd64 (1.0.0-2ubuntu2.3) ...
Selecting previously unselected package libgl1-mesa-glx:amd64.
Preparing to unpack .../066-libgl1-mesa-glx_19.2.8-0ubuntu0~18.04.3_amd64.deb ...
Unpacking libgl1-mesa-glx:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Selecting previously unselected package libxt6:amd64.
Preparing to unpack .../067-libxt6_1%3a1.1.5-1_amd64.deb ...
Unpacking libxt6:amd64 (1:1.1.5-1) ...
Selecting previously unselected package libxmu6:amd64.
Preparing to unpack .../068-libxmu6_2%3a1.1.2-2_amd64.deb ...
Unpacking libxmu6:amd64 (2:1.1.2-2) ...
Selecting previously unselected package libxpm4:amd64.
Preparing to unpack .../069-libxpm4_1%3a3.5.12-1_amd64.deb ...
Unpacking libxpm4:amd64 (1:3.5.12-1) ...
Selecting previously unselected package libxaw7:amd64.
Preparing to unpack .../070-libxaw7_2%3a1.0.13-1_amd64.deb ...
Unpacking libxaw7:amd64 (2:1.0.13-1) ...
Selecting previously unselected package libxcb-shape0:amd64.
Preparing to unpack .../071-libxcb-shape0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-shape0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcomposite1:amd64.
Preparing to unpack .../072-libxcomposite1_1%3a0.4.4-2_amd64.deb ...
Unpacking libxcomposite1:amd64 (1:0.4.4-2) ...
Selecting previously unselected package libxrandr2:amd64.
Preparing to unpack .../073-libxrandr2_2%3a1.5.1-1_amd64.deb ...
Unpacking libxrandr2:amd64 (2:1.5.1-1) ...
Selecting previously unselected package libxv1:amd64.
Preparing to unpack .../074-libxv1_2%3a1.0.11-1_amd64.deb ...
Unpacking libxv1:amd64 (2:1.0.11-1) ...
Selecting previously unselected package x11-utils.
Preparing to unpack .../075-x11-utils_7.7+3build1_amd64.deb ...
Unpacking x11-utils (7.7+3build1) ...
Selecting previously unselected package libatk-wrapper-java.
Preparing to unpack .../076-libatk-wrapper-java_0.33.3-20ubuntu0.1_all.deb ...
Unpacking libatk-wrapper-java (0.33.3-20ubuntu0.1) ...
Selecting previously unselected package libatk-wrapper-java-jni:amd64.
Preparing to unpack .../077-libatk-wrapper-java-jni_0.33.3-20ubuntu0.1_amd64.deb ...
Unpacking libatk-wrapper-java-jni:amd64 (0.33.3-20ubuntu0.1) ...
Selecting previously unselected package libflac8:amd64.
Preparing to unpack .../078-libflac8_1.3.2-1_amd64.deb ...
Unpacking libflac8:amd64 (1.3.2-1) ...
Selecting previously unselected package libgtk2.0-common.
Preparing to unpack .../079-libgtk2.0-common_2.24.32-1ubuntu1_all.deb ...
Unpacking libgtk2.0-common (2.24.32-1ubuntu1) ...
Selecting previously unselected package libxcursor1:amd64.
Preparing to unpack .../080-libxcursor1_1%3a1.1.15-1_amd64.deb ...
Unpacking libxcursor1:amd64 (1:1.1.15-1) ...
Selecting previously unselected package libgtk2.0-0:amd64.
Preparing to unpack .../081-libgtk2.0-0_2.24.32-1ubuntu1_amd64.deb ...
Unpacking libgtk2.0-0:amd64 (2.24.32-1ubuntu1) ...
Selecting previously unselected package libgail18:amd64.
Preparing to unpack .../082-libgail18_2.24.32-1ubuntu1_amd64.deb ...
Unpacking libgail18:amd64 (2.24.32-1ubuntu1) ...
Selecting previously unselected package libgail-common:amd64.
Preparing to unpack .../083-libgail-common_2.24.32-1ubuntu1_amd64.deb ...
Unpacking libgail-common:amd64 (2.24.32-1ubuntu1) ...
Selecting previously unselected package libgdk-pixbuf2.0-bin.
Preparing to unpack .../084-libgdk-pixbuf2.0-bin_2.36.11-2_amd64.deb ...
Unpacking libgdk-pixbuf2.0-bin (2.36.11-2) ...
Selecting previously unselected package libgif7:amd64.
Preparing to unpack .../085-libgif7_5.1.4-2ubuntu0.1_amd64.deb ...
Unpacking libgif7:amd64 (5.1.4-2ubuntu0.1) ...
Selecting previously unselected package libgtk2.0-bin.
Preparing to unpack .../086-libgtk2.0-bin_2.24.32-1ubuntu1_amd64.deb ...
Unpacking libgtk2.0-bin (2.24.32-1ubuntu1) ...
Selecting previously unselected package xorg-sgml-doctools.
Preparing to unpack .../087-xorg-sgml-doctools_1%3a1.11-1_all.deb ...
Unpacking xorg-sgml-doctools (1:1.11-1) ...
Selecting previously unselected package x11proto-dev.
Preparing to unpack .../088-x11proto-dev_2018.4-4_all.deb ...
Unpacking x11proto-dev (2018.4-4) ...
Selecting previously unselected package x11proto-core-dev.
Preparing to unpack .../089-x11proto-core-dev_2018.4-4_all.deb ...
Unpacking x11proto-core-dev (2018.4-4) ...
Selecting previously unselected package libice-dev:amd64.
Preparing to unpack .../090-libice-dev_2%3a1.0.9-2_amd64.deb ...
Unpacking libice-dev:amd64 (2:1.0.9-2) ...
Selecting previously unselected package libpthread-stubs0-dev:amd64.
Preparing to unpack .../091-libpthread-stubs0-dev_0.3-4_amd64.deb ...
Unpacking libpthread-stubs0-dev:amd64 (0.3-4) ...
Selecting previously unselected package libvorbis0a:amd64.
Preparing to unpack .../092-libvorbis0a_1.3.5-4.2_amd64.deb ...
Unpacking libvorbis0a:amd64 (1.3.5-4.2) ...
Selecting previously unselected package libvorbisenc2:amd64.
Preparing to unpack .../093-libvorbisenc2_1.3.5-4.2_amd64.deb ...
Unpacking libvorbisenc2:amd64 (1.3.5-4.2) ...
Selecting previously unselected package libsndfile1:amd64.
Preparing to unpack .../094-libsndfile1_1.0.28-4ubuntu0.18.04.1_amd64.deb ...
Unpacking libsndfile1:amd64 (1.0.28-4ubuntu0.18.04.1) ...
Selecting previously unselected package libpulse0:amd64.
Preparing to unpack .../095-libpulse0_1%3a11.1-1ubuntu7.8_amd64.deb ...
Unpacking libpulse0:amd64 (1:11.1-1ubuntu7.8) ...
Selecting previously unselected package libsm-dev:amd64.
Preparing to unpack .../096-libsm-dev_2%3a1.2.2-1_amd64.deb ...
Unpacking libsm-dev:amd64 (2:1.2.2-1) ...
Selecting previously unselected package libxau-dev:amd64.
Preparing to unpack .../097-libxau-dev_1%3a1.0.8-1_amd64.deb ...
Unpacking libxau-dev:amd64 (1:1.0.8-1) ...
Selecting previously unselected package libxdmcp-dev:amd64.
Preparing to unpack .../098-libxdmcp-dev_1%3a1.1.2-3_amd64.deb ...
Unpacking libxdmcp-dev:amd64 (1:1.1.2-3) ...
Selecting previously unselected package xtrans-dev.
Preparing to unpack .../099-xtrans-dev_1.3.5-1_all.deb ...
Unpacking xtrans-dev (1.3.5-1) ...
Selecting previously unselected package libxcb1-dev:amd64.
Preparing to unpack .../100-libxcb1-dev_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb1-dev:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libx11-dev:amd64.
Preparing to unpack .../101-libx11-dev_2%3a1.6.4-3ubuntu0.2_amd64.deb ...
Unpacking libx11-dev:amd64 (2:1.6.4-3ubuntu0.2) ...
Selecting previously unselected package libx11-doc.
Preparing to unpack .../102-libx11-doc_2%3a1.6.4-3ubuntu0.2_all.deb ...
Unpacking libx11-doc (2:1.6.4-3ubuntu0.2) ...
Selecting previously unselected package libxt-dev:amd64.
Preparing to unpack .../103-libxt-dev_1%3a1.1.5-1_amd64.deb ...
Unpacking libxt-dev:amd64 (1:1.1.5-1) ...
Selecting previously unselected package openjdk-8-jre:amd64.
Preparing to unpack .../104-openjdk-8-jre_8u252-b09-1~18.04_amd64.deb ...
Unpacking openjdk-8-jre:amd64 (8u252-b09-1~18.04) ...
Selecting previously unselected package openjdk-8-jdk-headless:amd64.
Preparing to unpack .../105-openjdk-8-jdk-headless_8u252-b09-1~18.04_amd64.deb ...
Unpacking openjdk-8-jdk-headless:amd64 (8u252-b09-1~18.04) ...
Selecting previously unselected package openjdk-8-jdk:amd64.
Preparing to unpack .../106-openjdk-8-jdk_8u252-b09-1~18.04_amd64.deb ...
Unpacking openjdk-8-jdk:amd64 (8u252-b09-1~18.04) ...
Setting up libxcb-present0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libglvnd0:amd64 (1.0.0-2ubuntu2.3) ...
Setting up libxinerama1:amd64 (2:1.1.3-1) ...
Setting up libxcb-dri2-0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libxcb-dri3-0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libxcb-glx0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libgtk2.0-common (2.24.32-1ubuntu1) ...
Setting up libxcb-render0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libasyncns0:amd64 (0.8-6) ...
Setting up libxdamage1:amd64 (1:1.1.4-3) ...
Setting up libxfixes3:amd64 (1:5.0.3-1) ...
Setting up libjbig0:amd64 (2.1-3.1build1) ...
Setting up libpthread-stubs0-dev:amd64 (0.3-4) ...
Setting up openjdk-8-jdk-headless:amd64 (8u252-b09-1~18.04) ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/idlj to provide /usr/bin/idlj (idlj) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jdeps to provide /usr/bin/jdeps (jdeps) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/wsimport to provide /usr/bin/wsimport (wsimport) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/rmic to provide /usr/bin/rmic (rmic) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jinfo to provide /usr/bin/jinfo (jinfo) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jsadebugd to provide /usr/bin/jsadebugd (jsadebugd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/native2ascii to provide /usr/bin/native2ascii (native2ascii) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jstat to provide /usr/bin/jstat (jstat) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javadoc to provide /usr/bin/javadoc (javadoc) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javah to provide /usr/bin/javah (javah) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/clhsdb to provide /usr/bin/clhsdb (clhsdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jstack to provide /usr/bin/jstack (jstack) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jrunscript to provide /usr/bin/jrunscript (jrunscript) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javac to provide /usr/bin/javac (javac) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javap to provide /usr/bin/javap (javap) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jar to provide /usr/bin/jar (jar) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/extcheck to provide /usr/bin/extcheck (extcheck) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/hsdb to provide /usr/bin/hsdb (hsdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/schemagen to provide /usr/bin/schemagen (schemagen) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jps to provide /usr/bin/jps (jps) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/xjc to provide /usr/bin/xjc (xjc) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jmap to provide /usr/bin/jmap (jmap) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jstatd to provide /usr/bin/jstatd (jstatd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jhat to provide /usr/bin/jhat (jhat) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jdb to provide /usr/bin/jdb (jdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/serialver to provide /usr/bin/serialver (serialver) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/wsgen to provide /usr/bin/wsgen (wsgen) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jcmd to provide /usr/bin/jcmd (jcmd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jarsigner to provide /usr/bin/jarsigner (jarsigner) in auto mode
Setting up libatspi2.0-0:amd64 (2.28.0-1) ...
Setting up at-spi2-core (2.28.0-1) ...
Setting up libasound2-data (1.1.3-5ubuntu0.5) ...
Setting up libxshmfence1:amd64 (1.3-1) ...
Setting up xorg-sgml-doctools (1:1.11-1) ...
Setting up libgdk-pixbuf2.0-common (2.36.11-2) ...
Setting up libdatrie1:amd64 (0.2.10-7) ...
Setting up libtiff5:amd64 (4.0.9-5ubuntu0.3) ...
Setting up libgif7:amd64 (5.1.4-2ubuntu0.1) ...
Setting up libglapi-mesa:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Setting up x11proto-dev (2018.4-4) ...
Setting up libasound2:amd64 (1.1.3-5ubuntu0.5) ...
Setting up libdrm-common (2.4.101-2~18.04.1) ...
Setting up libgraphite2-3:amd64 (1.3.11-2) ...
Setting up libcroco3:amd64 (0.6.12-2) ...
Setting up libxcb-sync1:amd64 (1.13-2~ubuntu18.04) ...
Setting up libogg0:amd64 (1.3.2-1) ...
Setting up libatk1.0-data (2.28.1-1) ...
Setting up libx11-xcb1:amd64 (2:1.6.4-3ubuntu0.2) ...
Setting up libpixman-1-0:amd64 (0.34.0-2) ...
Setting up xtrans-dev (1.3.5-1) ...
Setting up libxcursor1:amd64 (1:1.1.15-1) ...
Setting up libxdmcp-dev:amd64 (1:1.1.2-3) ...
Setting up libxxf86dga1:amd64 (2:1.1.4-1) ...
Setting up libatk1.0-0:amd64 (2.28.1-1) ...
Setting up libatk-bridge2.0-0:amd64 (2.26.2-1) ...
Setting up libice6:amd64 (2:1.0.9-2) ...
Setting up libfontenc1:amd64 (1:1.1.3-1) ...
Setting up libxcomposite1:amd64 (1:0.4.4-2) ...
Setting up libxcb-shm0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libxpm4:amd64 (1:3.5.12-1) ...
Setting up libx11-doc (2:1.6.4-3ubuntu0.2) ...
Setting up libxcb-shape0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libpciaccess0:amd64 (0.14-1) ...
Setting up libxv1:amd64 (2:1.0.11-1) ...
Setting up libsensors4:amd64 (1:3.4.0-4) ...
Setting up libthai-data (0.1.27-2) ...
Setting up libxxf86vm1:amd64 (1:1.1.4-1) ...
Setting up libllvm9:amd64 (1:9-2~ubuntu18.04.2) ...
Setting up libxft2:amd64 (2.3.2-1) ...
Setting up fonts-dejavu-extra (2.37-1) ...
Setting up libvorbis0a:amd64 (1.3.5-4.2) ...
Setting up hicolor-icon-theme (0.17-2) ...
Setting up libxrandr2:amd64 (2:1.5.1-1) ...
Setting up fontconfig (2.12.6-0ubuntu2) ...
Regenerating fonts cache... done.
Setting up libcairo2:amd64 (1.15.10-2ubuntu0.1) ...
Setting up libsm6:amd64 (2:1.2.2-1) ...
Setting up x11proto-core-dev (2018.4-4) ...
Setting up libgdk-pixbuf2.0-0:amd64 (2.36.11-2) ...
Setting up libflac8:amd64 (1.3.2-1) ...
Setting up libgdk-pixbuf2.0-bin (2.36.11-2) ...
Setting up libharfbuzz0b:amd64 (1.7.2-1ubuntu1) ...
Setting up libxau-dev:amd64 (1:1.0.8-1) ...
Setting up libthai0:amd64 (0.1.27-2) ...
Setting up libdrm2:amd64 (2.4.101-2~18.04.1) ...
Setting up libdrm-intel1:amd64 (2.4.101-2~18.04.1) ...
Setting up gtk-update-icon-cache (3.22.30-1ubuntu4) ...
Setting up libice-dev:amd64 (2:1.0.9-2) ...
Setting up libpango-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Setting up libxt6:amd64 (1:1.1.5-1) ...
Setting up libxcb1-dev:amd64 (1.13-2~ubuntu18.04) ...
Setting up libdrm-radeon1:amd64 (2.4.101-2~18.04.1) ...
Setting up libx11-dev:amd64 (2:1.6.4-3ubuntu0.2) ...
Setting up libvorbisenc2:amd64 (1.3.5-4.2) ...
Setting up libdrm-nouveau2:amd64 (2.4.101-2~18.04.1) ...
Setting up libsm-dev:amd64 (2:1.2.2-1) ...
Setting up libdrm-amdgpu1:amd64 (2.4.101-2~18.04.1) ...
Setting up libgl1-mesa-dri:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Setting up libxmu6:amd64 (2:1.1.2-2) ...
Setting up libpangoft2-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Setting up libsndfile1:amd64 (1.0.28-4ubuntu0.18.04.1) ...
Setting up libglx-mesa0:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Setting up libxaw7:amd64 (2:1.0.13-1) ...
Setting up libxt-dev:amd64 (1:1.1.5-1) ...
Setting up libpangocairo-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Setting up libpulse0:amd64 (1:11.1-1ubuntu7.8) ...
Setting up libglx0:amd64 (1.0.0-2ubuntu2.3) ...
Setting up librsvg2-2:amd64 (2.40.20-2) ...
Setting up librsvg2-common:amd64 (2.40.20-2) ...
Setting up libgl1:amd64 (1.0.0-2ubuntu2.3) ...
Setting up x11-utils (7.7+3build1) ...
Setting up libgl1-mesa-glx:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Setting up libatk-wrapper-java (0.33.3-20ubuntu0.1) ...
Setting up libatk-wrapper-java-jni:amd64 (0.33.3-20ubuntu0.1) ...
Setting up adwaita-icon-theme (3.28.0-1ubuntu1) ...
update-alternatives: using /usr/share/icons/Adwaita/cursor.theme to provide /usr/share/icons/default/index.theme (x-cursor-theme) in auto mode
Setting up libgtk2.0-0:amd64 (2.24.32-1ubuntu1) ...
Setting up libgail18:amd64 (2.24.32-1ubuntu1) ...
Setting up libgail-common:amd64 (2.24.32-1ubuntu1) ...
Setting up humanity-icon-theme (0.6.15) ...
Setting up openjdk-8-jre:amd64 (8u252-b09-1~18.04) ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/policytool to provide /usr/bin/policytool (policytool) in auto mode
Setting up libgtk2.0-bin (2.24.32-1ubuntu1) ...
Setting up openjdk-8-jdk:amd64 (8u252-b09-1~18.04) ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/appletviewer to provide /usr/bin/appletviewer (appletviewer) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jconsole to provide /usr/bin/jconsole (jconsole) in auto mode
Setting up ubuntu-mono (16.10+18.04.20181005-0ubuntu1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Processing triggers for libgdk-pixbuf2.0-0:amd64 (2.36.11-2) ...
ubuntu@ip-172-31-39-83:~$ export JAVA_HOME=/usr/lib/jvm/java-8-openjdk
ubuntu@ip-172-31-39-83:~$ export PATH=$PATH:/usr/lib/jvm/java-8-openjdk/bin
ubuntu@ip-172-31-39-83:~$ javac -version
javac 1.8.0_252
ubuntu@ip-172-31-39-83:~$ wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
OK
ubuntu@ip-172-31-39-83:~$ sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
ubuntu@ip-172-31-39-83:~$ sudo apt update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease
Ign:4 http://pkg.jenkins-ci.org/debian-stable binary/ InRelease
Get:5 http://pkg.jenkins-ci.org/debian-stable binary/ Release [2044 B]
Get:6 http://pkg.jenkins-ci.org/debian-stable binary/ Release.gpg [195 B]
Get:7 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]
Hit:8 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic InRelease
Get:9 http://pkg.jenkins-ci.org/debian-stable binary/ Packages [17.6 kB]
Fetched 109 kB in 1s (159 kB/s)
Reading package lists... Done
Building dependency tree
Reading state information... Done
71 packages can be upgraded. Run 'apt list --upgradable' to see them.
ubuntu@ip-172-31-39-83:~$ sudo apt install jenkins
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  daemon
The following NEW packages will be installed:
  daemon jenkins
0 upgraded, 2 newly installed, 0 to remove and 71 not upgraded.
Need to get 65.7 MB of archives.
After this operation, 66.8 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 daemon amd64 0.6.4-1build1 [99.5 kB]
Get:2 http://pkg.jenkins-ci.org/debian-stable binary/ jenkins 2.235.1 [65.6 MB]
Fetched 65.7 MB in 1min 12s (908 kB/s)
Selecting previously unselected package daemon.
(Reading database ... 72591 files and directories currently installed.)
Preparing to unpack .../daemon_0.6.4-1build1_amd64.deb ...
Unpacking daemon (0.6.4-1build1) ...
Selecting previously unselected package jenkins.
Preparing to unpack .../jenkins_2.235.1_all.deb ...
Unpacking jenkins (2.235.1) ...
Setting up daemon (0.6.4-1build1) ...
Setting up jenkins (2.235.1) ...
Processing triggers for systemd (237-3ubuntu10.39) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for ureadahead (0.100.0-21) ...
ubuntu@ip-172-31-39-83:~$
ubuntu@ip-172-31-39-83:~$ ubuntu@ip-172-31-39-83:~$


ubuntu@ip-172-31-39-83:~$: command not found
ubuntu@ip-172-31-39-83:~$
ubuntu@ip-172-31-39-83:~$
ubuntu@ip-172-31-39-83:~$ sudo systemctl start jenkins
ubuntu@ip-172-31-39-83:~$ /var/lib/jenkins/secrets/initialAdminPassword
-bash: /var/lib/jenkins/secrets/initialAdminPassword: Permission denied
ubuntu@ip-172-31-39-83:~$
ubuntu@ip-172-31-39-83:~$ cat /var/lib/jenkins/secrets/initialAdminPassword
cat: /var/lib/jenkins/secrets/initialAdminPassword: Permission denied
ubuntu@ip-172-31-39-83:~$
ubuntu@ip-172-31-39-83:~$ su jenkins
Password:



su: Authentication failure
ubuntu@ip-172-31-39-83:~$
ubuntu@ip-172-31-39-83:~$
ubuntu@ip-172-31-39-83:~$
ubuntu@ip-172-31-39-83:~$
ubuntu@ip-172-31-39-83:~$ sudo su jenkins
jenkins@ip-172-31-39-83:/home/ubuntu$ cd
jenkins@ip-172-31-39-83:~$ cat /var/lib/jenkins/secrets/initialAdminPassword
f4f0fab25aa9414dbdbefbe73a37f40c
jenkins@ip-172-31-39-83:~$ ^C
jenkins@ip-172-31-39-83:~$ client_loop: send disconnect: Connection reset by peer

PuvvulaM@HBADT4401133 MINGW64 ~/Downloads
$ ssh -i "awsnew.pem" ubuntu@ec2-18-224-228-96.us-east-2.compute.amazonaws.com
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-1065-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Jun 19 19:22:29 UTC 2020

  System load:  0.0               Processes:           101
  Usage of /:   24.8% of 7.69GB   Users logged in:     1
  Memory usage: 54%               IP address for ens5: 172.31.39.83
  Swap usage:   0%


76 packages can be updated.
43 updates are security updates.


Last login: Fri Jun 19 18:09:04 2020 from 223.237.61.40
ubuntu@ip-172-31-39-83:~$ /var/lib/jenkins/.ssh/known_hosts
-bash: /var/lib/jenkins/.ssh/known_hosts: No such file or directory
ubuntu@ip-172-31-39-83:~$ cd /var/lib/jenkins/.ssh
-bash: cd: /var/lib/jenkins/.ssh: No such file or directory
ubuntu@ip-172-31-39-83:~$ ls
ubuntu@ip-172-31-39-83:~$ sudo su jenkins
jenkins@ip-172-31-39-83:/home/ubuntu$ cd
jenkins@ip-172-31-39-83:~$ pwd
/var/lib/jenkins
jenkins@ip-172-31-39-83:~$ mkdir .ssh
jenkins@ip-172-31-39-83:~$
jenkins@ip-172-31-39-83:~$ cd .ssh
jenkins@ip-172-31-39-83:~/.ssh$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/var/lib/jenkins/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /var/lib/jenkins/.ssh/id_rsa.
Your public key has been saved in /var/lib/jenkins/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:856/ZC7LlNm6a7nlrSiPdVWUHl3BZvmGUhoG8lVeCJI jenkins@ip-172-31-39-83
The key's randomart image is:
+---[RSA 2048]----+
|        . ooooooX|
|         oEoo.oX.|
|          .. +=.+|
|            o .oo|
|        S    ... |
|         o + .   |
|          *.*    |
|        .*+@ .   |
|        .+%B*o.  |
+----[SHA256]-----+
jenkins@ip-172-31-39-83:~/.ssh$
jenkins@ip-172-31-39-83:~/.ssh$ touch n
jenkins@ip-172-31-39-83:~/.ssh$ touch /var/lib/jenkins/.ssh/known_hosts
jenkins@ip-172-31-39-83:~/.ssh$



maven
PuvvulaM@HBADT4401133 MINGW64 ~/Downloads
$ ssh -i "awsnew.pem" @ec2-3-128-28-116.us-east-2.compute.amazonaws.com
usage: ssh [-46AaCfGgKkMNnqsTtVvXxYy] [-B bind_interface]
           [-b bind_address] [-c cipher_spec] [-D [bind_address:]port]
           [-E log_file] [-e escape_char] [-F configfile] [-I pkcs11]
           [-i identity_file] [-J [user@]host[:port]] [-L address]
           [-l login_name] [-m mac_spec] [-O ctl_cmd] [-o option] [-p port]
           [-Q query_option] [-R address] [-S ctl_path] [-W host:port]
           [-w local_tun[:remote_tun]] destination [command]

PuvvulaM@HBADT4401133 MINGW64 ~/Downloads
$ ssh -i "awsnew.pem" @ec2-3-128-28-116.us-east-2.compute.amazonaws.com
usage: ssh [-46AaCfGgKkMNnqsTtVvXxYy] [-B bind_interface]
           [-b bind_address] [-c cipher_spec] [-D [bind_address:]port]
           [-E log_file] [-e escape_char] [-F configfile] [-I pkcs11]
           [-i identity_file] [-J [user@]host[:port]] [-L address]
           [-l login_name] [-m mac_spec] [-O ctl_cmd] [-o option] [-p port]
           [-Q query_option] [-R address] [-S ctl_path] [-W host:port]
           [-w local_tun[:remote_tun]] destination [command]

PuvvulaM@HBADT4401133 MINGW64 ~/Downloads
$ ssh -i "awsnew.pem" ubuntu@ec2-3-128-28-116.us-east-2.compute.amazonaws.com
The authenticity of host 'ec2-3-128-28-116.us-east-2.compute.amazonaws.com (3.128.28.116)' can't be established.
ECDSA key fingerprint is SHA256:T88rn8eMqTN8dypDtdz8N25ZSX+TJIz0usxqZG5MCyk.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'ec2-3-128-28-116.us-east-2.compute.amazonaws.com,3.128.28.116' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-1065-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Jun 19 18:46:00 UTC 2020

  System load:  0.92              Processes:           89
  Usage of /:   13.8% of 7.69GB   Users logged in:     0
  Memory usage: 15%               IP address for eth0: 172.31.16.80
  Swap usage:   0%

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

ubuntu@ip-172-31-16-80:~$ sudo apt-get update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]
Get:4 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 Packages [8570 kB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe Translation-en [4941 kB]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/multiverse amd64 Packages [151 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/multiverse Translation-en [108 kB]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 Packages [969 kB]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main Translation-en [329 kB]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/restricted amd64 Packages [60.5 kB]
Get:12 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/restricted Translation-en [14.7 kB]
Get:13 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 Packages [1085 kB]
Get:14 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe Translation-en [337 kB]
Get:15 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 Packages [15.9 kB]
Get:16 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/multiverse Translation-en [6420 B]
Get:17 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/main amd64 Packages [7516 B]
Get:18 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/main Translation-en [4764 B]
Get:19 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/universe amd64 Packages [7484 B]
Get:20 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/universe Translation-en [4436 B]
Get:21 http://security.ubuntu.com/ubuntu bionic-security/main amd64 Packages [748 kB]
Get:22 http://security.ubuntu.com/ubuntu bionic-security/main Translation-en [237 kB]
Get:23 http://security.ubuntu.com/ubuntu bionic-security/restricted amd64 Packages [50.8 kB]
Get:24 http://security.ubuntu.com/ubuntu bionic-security/restricted Translation-en [12.3 kB]
Get:25 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 Packages [673 kB]
Get:26 http://security.ubuntu.com/ubuntu bionic-security/universe Translation-en [223 kB]
Get:27 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 Packages [7808 B]
Get:28 http://security.ubuntu.com/ubuntu bionic-security/multiverse Translation-en [2856 B]
Fetched 18.8 MB in 4s (4765 kB/s)
Reading package lists... Done
ubuntu@ip-172-31-16-80:~$ sudo apt install openjdk-8-jre-headless
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  ca-certificates-java fontconfig-config fonts-dejavu-core java-common libavahi-client3 libavahi-common-data libavahi-common3 libcups2 libfontconfig1 libjpeg-turbo8 libjpeg8 liblcms2-2
  libnspr4 libnss3 libpcsclite1 libxi6 libxrender1 libxtst6 x11-common
Suggested packages:
  default-jre cups-common liblcms2-utils pcscd libnss-mdns fonts-dejavu-extra fonts-ipafont-gothic fonts-ipafont-mincho fonts-wqy-microhei fonts-wqy-zenhei fonts-indic
The following NEW packages will be installed:
  ca-certificates-java fontconfig-config fonts-dejavu-core java-common libavahi-client3 libavahi-common-data libavahi-common3 libcups2 libfontconfig1 libjpeg-turbo8 libjpeg8 liblcms2-2
  libnspr4 libnss3 libpcsclite1 libxi6 libxrender1 libxtst6 openjdk-8-jre-headless x11-common
0 upgraded, 20 newly installed, 0 to remove and 73 not upgraded.
Need to get 30.7 MB of archives.
After this operation, 111 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libjpeg-turbo8 amd64 1.5.2-0ubuntu5.18.04.4 [110 kB]
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 java-common all 0.68ubuntu1~18.04.1 [14.5 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libavahi-common-data amd64 0.7-3.1ubuntu1.2 [22.1 kB]
Get:4 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libavahi-common3 amd64 0.7-3.1ubuntu1.2 [21.6 kB]
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libavahi-client3 amd64 0.7-3.1ubuntu1.2 [25.2 kB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libcups2 amd64 2.2.7-1ubuntu2.8 [211 kB]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 liblcms2-2 amd64 2.9-1ubuntu0.1 [139 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libjpeg8 amd64 8c-2ubuntu8 [2194 B]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 fonts-dejavu-core all 2.37-1 [1041 kB]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 fontconfig-config all 2.12.6-0ubuntu2 [55.8 kB]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libfontconfig1 amd64 2.12.6-0ubuntu2 [137 kB]
Get:12 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libnspr4 amd64 2:4.18-1ubuntu1 [112 kB]
Get:13 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libnss3 amd64 2:3.35-2ubuntu2.8 [1136 kB]
Get:14 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libpcsclite1 amd64 1.8.23-1 [21.3 kB]
Get:15 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxi6 amd64 2:1.7.9-1 [29.2 kB]
Get:16 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxrender1 amd64 1:0.9.10-1 [18.7 kB]
Get:17 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 x11-common all 1:7.7+19ubuntu7.1 [22.5 kB]
Get:18 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxtst6 amd64 2:1.2.3-1 [12.8 kB]
Get:19 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 openjdk-8-jre-headless amd64 8u252-b09-1~18.04 [27.5 MB]
Get:20 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 ca-certificates-java all 20180516ubuntu1~18.04.1 [12.2 kB]
Fetched 30.7 MB in 1s (51.6 MB/s)
Selecting previously unselected package libjpeg-turbo8:amd64.
(Reading database ... 56588 files and directories currently installed.)
Preparing to unpack .../00-libjpeg-turbo8_1.5.2-0ubuntu5.18.04.4_amd64.deb ...
Unpacking libjpeg-turbo8:amd64 (1.5.2-0ubuntu5.18.04.4) ...
Selecting previously unselected package java-common.
Preparing to unpack .../01-java-common_0.68ubuntu1~18.04.1_all.deb ...
Unpacking java-common (0.68ubuntu1~18.04.1) ...
Selecting previously unselected package libavahi-common-data:amd64.
Preparing to unpack .../02-libavahi-common-data_0.7-3.1ubuntu1.2_amd64.deb ...
Unpacking libavahi-common-data:amd64 (0.7-3.1ubuntu1.2) ...
Selecting previously unselected package libavahi-common3:amd64.
Preparing to unpack .../03-libavahi-common3_0.7-3.1ubuntu1.2_amd64.deb ...
Unpacking libavahi-common3:amd64 (0.7-3.1ubuntu1.2) ...
Selecting previously unselected package libavahi-client3:amd64.
Preparing to unpack .../04-libavahi-client3_0.7-3.1ubuntu1.2_amd64.deb ...
Unpacking libavahi-client3:amd64 (0.7-3.1ubuntu1.2) ...
Selecting previously unselected package libcups2:amd64.
Preparing to unpack .../05-libcups2_2.2.7-1ubuntu2.8_amd64.deb ...
Unpacking libcups2:amd64 (2.2.7-1ubuntu2.8) ...
Selecting previously unselected package liblcms2-2:amd64.
Preparing to unpack .../06-liblcms2-2_2.9-1ubuntu0.1_amd64.deb ...
Unpacking liblcms2-2:amd64 (2.9-1ubuntu0.1) ...
Selecting previously unselected package libjpeg8:amd64.
Preparing to unpack .../07-libjpeg8_8c-2ubuntu8_amd64.deb ...
Unpacking libjpeg8:amd64 (8c-2ubuntu8) ...
Selecting previously unselected package fonts-dejavu-core.
Preparing to unpack .../08-fonts-dejavu-core_2.37-1_all.deb ...
Unpacking fonts-dejavu-core (2.37-1) ...
Selecting previously unselected package fontconfig-config.
Preparing to unpack .../09-fontconfig-config_2.12.6-0ubuntu2_all.deb ...
Unpacking fontconfig-config (2.12.6-0ubuntu2) ...
Selecting previously unselected package libfontconfig1:amd64.
Preparing to unpack .../10-libfontconfig1_2.12.6-0ubuntu2_amd64.deb ...
Unpacking libfontconfig1:amd64 (2.12.6-0ubuntu2) ...
Selecting previously unselected package libnspr4:amd64.
Preparing to unpack .../11-libnspr4_2%3a4.18-1ubuntu1_amd64.deb ...
Unpacking libnspr4:amd64 (2:4.18-1ubuntu1) ...
Selecting previously unselected package libnss3:amd64.
Preparing to unpack .../12-libnss3_2%3a3.35-2ubuntu2.8_amd64.deb ...
Unpacking libnss3:amd64 (2:3.35-2ubuntu2.8) ...
Selecting previously unselected package libpcsclite1:amd64.
Preparing to unpack .../13-libpcsclite1_1.8.23-1_amd64.deb ...
Unpacking libpcsclite1:amd64 (1.8.23-1) ...
Selecting previously unselected package libxi6:amd64.
Preparing to unpack .../14-libxi6_2%3a1.7.9-1_amd64.deb ...
Unpacking libxi6:amd64 (2:1.7.9-1) ...
Selecting previously unselected package libxrender1:amd64.
Preparing to unpack .../15-libxrender1_1%3a0.9.10-1_amd64.deb ...
Unpacking libxrender1:amd64 (1:0.9.10-1) ...
Selecting previously unselected package x11-common.
Preparing to unpack .../16-x11-common_1%3a7.7+19ubuntu7.1_all.deb ...
dpkg-query: no packages found matching nux-tools
Unpacking x11-common (1:7.7+19ubuntu7.1) ...
Selecting previously unselected package libxtst6:amd64.
Preparing to unpack .../17-libxtst6_2%3a1.2.3-1_amd64.deb ...
Unpacking libxtst6:amd64 (2:1.2.3-1) ...
Selecting previously unselected package openjdk-8-jre-headless:amd64.
Preparing to unpack .../18-openjdk-8-jre-headless_8u252-b09-1~18.04_amd64.deb ...
Unpacking openjdk-8-jre-headless:amd64 (8u252-b09-1~18.04) ...
Selecting previously unselected package ca-certificates-java.
Preparing to unpack .../19-ca-certificates-java_20180516ubuntu1~18.04.1_all.deb ...
Unpacking ca-certificates-java (20180516ubuntu1~18.04.1) ...
Setting up libxi6:amd64 (2:1.7.9-1) ...
Setting up liblcms2-2:amd64 (2.9-1ubuntu0.1) ...
Setting up libpcsclite1:amd64 (1.8.23-1) ...
Setting up fonts-dejavu-core (2.37-1) ...
Setting up java-common (0.68ubuntu1~18.04.1) ...
Setting up libjpeg-turbo8:amd64 (1.5.2-0ubuntu5.18.04.4) ...
Setting up libnspr4:amd64 (2:4.18-1ubuntu1) ...
Setting up libxrender1:amd64 (1:0.9.10-1) ...
Setting up x11-common (1:7.7+19ubuntu7.1) ...
update-rc.d: warning: start and stop actions are no longer supported; falling back to defaults
Setting up libavahi-common-data:amd64 (0.7-3.1ubuntu1.2) ...
Setting up libjpeg8:amd64 (8c-2ubuntu8) ...
Setting up fontconfig-config (2.12.6-0ubuntu2) ...
Setting up libnss3:amd64 (2:3.35-2ubuntu2.8) ...
Setting up libxtst6:amd64 (2:1.2.3-1) ...
Setting up libavahi-common3:amd64 (0.7-3.1ubuntu1.2) ...
Setting up libfontconfig1:amd64 (2.12.6-0ubuntu2) ...
Setting up libavahi-client3:amd64 (0.7-3.1ubuntu1.2) ...
Setting up libcups2:amd64 (2.2.7-1ubuntu2.8) ...
Setting up ca-certificates-java (20180516ubuntu1~18.04.1) ...
head: cannot open '/etc/ssl/certs/java/cacerts' for reading: No such file or directory
Adding debian:OpenTrust_Root_CA_G2.pem
Adding debian:Starfield_Root_Certificate_Authority_-_G2.pem
Adding debian:GeoTrust_Universal_CA.pem
Adding debian:TrustCor_RootCert_CA-1.pem
Adding debian:T-TeleSec_GlobalRoot_Class_3.pem
Adding debian:TrustCor_ECA-1.pem
Adding debian:QuoVadis_Root_CA_1_G3.pem
Adding debian:Certigna.pem
Adding debian:Staat_der_Nederlanden_Root_CA_-_G2.pem
Adding debian:CA_Disig_Root_R2.pem
Adding debian:D-TRUST_Root_Class_3_CA_2_EV_2009.pem
Adding debian:Hellenic_Academic_and_Research_Institutions_RootCA_2015.pem
Adding debian:Visa_eCommerce_Root.pem
Adding debian:Comodo_AAA_Services_root.pem
Adding debian:Autoridad_de_Certificacion_Firmaprofesional_CIF_A62634068.pem
Adding debian:Actalis_Authentication_Root_CA.pem
Adding debian:DigiCert_Assured_ID_Root_G3.pem
Adding debian:Hongkong_Post_Root_CA_1.pem
Adding debian:thawte_Primary_Root_CA_-_G2.pem
Adding debian:Certum_Trusted_Network_CA_2.pem
Adding debian:Global_Chambersign_Root_-_2008.pem
Adding debian:DigiCert_Trusted_Root_G4.pem
Adding debian:DigiCert_Global_Root_G2.pem
Adding debian:Amazon_Root_CA_2.pem
Adding debian:TeliaSonera_Root_CA_v1.pem
Adding debian:QuoVadis_Root_CA_2.pem
Adding debian:Secure_Global_CA.pem
Adding debian:COMODO_RSA_Certification_Authority.pem
Adding debian:GDCA_TrustAUTH_R5_ROOT.pem
Adding debian:E-Tugra_Certification_Authority.pem
Adding debian:ACCVRAIZ1.pem
Adding debian:LuxTrust_Global_Root_2.pem
Adding debian:EE_Certification_Centre_Root_CA.pem
Adding debian:AffirmTrust_Networking.pem
Adding debian:Starfield_Class_2_CA.pem
Adding debian:Sonera_Class_2_Root_CA.pem
Adding debian:NetLock_Arany_=Class_Gold=_Főtanúsítvány.pem
Adding debian:GeoTrust_Global_CA.pem
Adding debian:XRamp_Global_CA_Root.pem
Adding debian:OpenTrust_Root_CA_G1.pem
Adding debian:Trustis_FPS_Root_CA.pem
Adding debian:COMODO_ECC_Certification_Authority.pem
Adding debian:GeoTrust_Primary_Certification_Authority_-_G3.pem
Adding debian:DigiCert_Global_Root_CA.pem
Adding debian:QuoVadis_Root_CA.pem
Adding debian:TWCA_Global_Root_CA.pem
Adding debian:ePKI_Root_Certification_Authority.pem
Adding debian:SwissSign_Silver_CA_-_G2.pem
Adding debian:Certum_Trusted_Network_CA.pem
Adding debian:Certplus_Root_CA_G1.pem
Adding debian:IdenTrust_Public_Sector_Root_CA_1.pem
Adding debian:DST_Root_CA_X3.pem
Adding debian:AffirmTrust_Commercial.pem
Adding debian:QuoVadis_Root_CA_2_G3.pem
Adding debian:OpenTrust_Root_CA_G3.pem
Adding debian:TrustCor_RootCert_CA-2.pem
Adding debian:Certplus_Class_2_Primary_CA.pem
Adding debian:CFCA_EV_ROOT.pem
Adding debian:Hellenic_Academic_and_Research_Institutions_RootCA_2011.pem
Adding debian:USERTrust_RSA_Certification_Authority.pem
Adding debian:Verisign_Class_3_Public_Primary_Certification_Authority_-_G3.pem
Adding debian:Amazon_Root_CA_1.pem
Adding debian:Entrust.net_Premium_2048_Secure_Server_CA.pem
Adding debian:Certinomis_-_Root_CA.pem
Adding debian:AddTrust_External_Root.pem
Adding debian:GlobalSign_ECC_Root_CA_-_R4.pem
Adding debian:TWCA_Root_Certification_Authority.pem
Adding debian:SSL.com_Root_Certification_Authority_RSA.pem
Adding debian:certSIGN_ROOT_CA.pem
Adding debian:QuoVadis_Root_CA_3.pem
Adding debian:QuoVadis_Root_CA_3_G3.pem
Adding debian:Microsec_e-Szigno_Root_CA_2009.pem
Adding debian:SSL.com_Root_Certification_Authority_ECC.pem
Adding debian:Go_Daddy_Root_Certificate_Authority_-_G2.pem
Adding debian:Buypass_Class_2_Root_CA.pem
Adding debian:DigiCert_Global_Root_G3.pem
Adding debian:Starfield_Services_Root_Certificate_Authority_-_G2.pem
Adding debian:Deutsche_Telekom_Root_CA_2.pem
Adding debian:ISRG_Root_X1.pem
Adding debian:Cybertrust_Global_Root.pem
Adding debian:AC_RAIZ_FNMT-RCM.pem
Adding debian:DigiCert_High_Assurance_EV_Root_CA.pem
Adding debian:SecureSign_RootCA11.pem
Adding debian:TÜRKTRUST_Elektronik_Sertifika_Hizmet_Sağlayıcısı_H5.pem
Adding debian:GeoTrust_Universal_CA_2.pem
Adding debian:TUBITAK_Kamu_SM_SSL_Kok_Sertifikasi_-_Surum_1.pem
Adding debian:Security_Communication_Root_CA.pem
Adding debian:AffirmTrust_Premium.pem
Adding debian:VeriSign_Universal_Root_Certification_Authority.pem
Adding debian:VeriSign_Class_3_Public_Primary_Certification_Authority_-_G5.pem
Adding debian:GlobalSign_ECC_Root_CA_-_R5.pem
Adding debian:Entrust_Root_Certification_Authority.pem
Adding debian:GeoTrust_Primary_Certification_Authority.pem
Adding debian:Go_Daddy_Class_2_CA.pem
Adding debian:COMODO_Certification_Authority.pem
Adding debian:GlobalSign_Root_CA_-_R2.pem
Adding debian:SwissSign_Gold_CA_-_G2.pem
Adding debian:D-TRUST_Root_Class_3_CA_2_2009.pem
Adding debian:VeriSign_Class_3_Public_Primary_Certification_Authority_-_G4.pem
Adding debian:GeoTrust_Primary_Certification_Authority_-_G2.pem
Adding debian:Entrust_Root_Certification_Authority_-_EC1.pem
Adding debian:thawte_Primary_Root_CA.pem
Adding debian:Security_Communication_RootCA2.pem
Adding debian:Certplus_Root_CA_G2.pem
Adding debian:Chambers_of_Commerce_Root_-_2008.pem
Adding debian:Entrust_Root_Certification_Authority_-_G2.pem
Adding debian:Taiwan_GRCA.pem
Adding debian:Hellenic_Academic_and_Research_Institutions_ECC_RootCA_2015.pem
Adding debian:DigiCert_Assured_ID_Root_G2.pem
Adding debian:Baltimore_CyberTrust_Root.pem
Adding debian:Network_Solutions_Certificate_Authority.pem
Adding debian:GlobalSign_Root_CA_-_R3.pem
Adding debian:IdenTrust_Commercial_Root_CA_1.pem
Adding debian:SSL.com_EV_Root_Certification_Authority_ECC.pem
Adding debian:Amazon_Root_CA_4.pem
Adding debian:GlobalSign_Root_CA.pem
Adding debian:thawte_Primary_Root_CA_-_G3.pem
Adding debian:Atos_TrustedRoot_2011.pem
Adding debian:Staat_der_Nederlanden_Root_CA_-_G3.pem
Adding debian:SecureTrust_CA.pem
Adding debian:Staat_der_Nederlanden_EV_Root_CA.pem
Adding debian:SZAFIR_ROOT_CA2.pem
Adding debian:DigiCert_Assured_ID_Root_CA.pem
Adding debian:Buypass_Class_3_Root_CA.pem
Adding debian:USERTrust_ECC_Certification_Authority.pem
Adding debian:T-TeleSec_GlobalRoot_Class_2.pem
Adding debian:Amazon_Root_CA_3.pem
Adding debian:EC-ACC.pem
Adding debian:SSL.com_EV_Root_Certification_Authority_RSA_R2.pem
Adding debian:AffirmTrust_Premium_ECC.pem
Adding debian:OISTE_WISeKey_Global_Root_GB_CA.pem
Adding debian:Izenpe.com.pem
Adding debian:OISTE_WISeKey_Global_Root_GA_CA.pem
done.
Processing triggers for ureadahead (0.100.0-21) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Processing triggers for systemd (237-3ubuntu10.39) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for ca-certificates (20180409) ...
Updating certificates in /etc/ssl/certs...
0 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...

done.
done.
Setting up openjdk-8-jre-headless:amd64 (8u252-b09-1~18.04) ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/rmid to provide /usr/bin/rmid (rmid) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java to provide /usr/bin/java (java) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/keytool to provide /usr/bin/keytool (keytool) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/jjs to provide /usr/bin/jjs (jjs) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/pack200 to provide /usr/bin/pack200 (pack200) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/rmiregistry to provide /usr/bin/rmiregistry (rmiregistry) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/unpack200 to provide /usr/bin/unpack200 (unpack200) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/orbd to provide /usr/bin/orbd (orbd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/servertool to provide /usr/bin/servertool (servertool) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/tnameserv to provide /usr/bin/tnameserv (tnameserv) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/jexec to provide /usr/bin/jexec (jexec) in auto mode
ubuntu@ip-172-31-16-80:~$ sudo add-apt-repository ppa:openjdk-r/ppa

 More info: https://launchpad.net/~openjdk-r/+archive/ubuntu/ppa
Press [ENTER] to continue or Ctrl-c to cancel adding it.

Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease
Get:4 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic InRelease [15.4 kB]
Hit:5 http://security.ubuntu.com/ubuntu bionic-security InRelease
Get:6 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic/main amd64 Packages [9372 B]
Get:7 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic/main Translation-en [1360 B]
Fetched 26.1 kB in 1s (36.7 kB/s)
Reading package lists... Done
ubuntu@ip-172-31-16-80:~$ sudo apt-get install openjdk-8-jdk
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  adwaita-icon-theme at-spi2-core fontconfig fonts-dejavu-extra gtk-update-icon-cache hicolor-icon-theme humanity-icon-theme libasound2 libasound2-data libasyncns0 libatk-bridge2.0-0
  libatk-wrapper-java libatk-wrapper-java-jni libatk1.0-0 libatk1.0-data libatspi2.0-0 libcairo2 libcroco3 libdatrie1 libdrm-amdgpu1 libdrm-common libdrm-intel1 libdrm-nouveau2
  libdrm-radeon1 libdrm2 libflac8 libfontenc1 libgail-common libgail18 libgdk-pixbuf2.0-0 libgdk-pixbuf2.0-bin libgdk-pixbuf2.0-common libgif7 libgl1 libgl1-mesa-dri libgl1-mesa-glx
  libglapi-mesa libglvnd0 libglx-mesa0 libglx0 libgraphite2-3 libgtk2.0-0 libgtk2.0-bin libgtk2.0-common libharfbuzz0b libice-dev libice6 libjbig0 libllvm9 libogg0 libpango-1.0-0
  libpangocairo-1.0-0 libpangoft2-1.0-0 libpciaccess0 libpixman-1-0 libpthread-stubs0-dev libpulse0 librsvg2-2 librsvg2-common libsensors4 libsm-dev libsm6 libsndfile1 libthai-data libthai0
  libtiff5 libvorbis0a libvorbisenc2 libx11-dev libx11-doc libx11-xcb1 libxau-dev libxaw7 libxcb-dri2-0 libxcb-dri3-0 libxcb-glx0 libxcb-present0 libxcb-render0 libxcb-shape0 libxcb-shm0
  libxcb-sync1 libxcb1-dev libxcomposite1 libxcursor1 libxdamage1 libxdmcp-dev libxfixes3 libxft2 libxinerama1 libxmu6 libxpm4 libxrandr2 libxshmfence1 libxt-dev libxt6 libxv1 libxxf86dga1
  libxxf86vm1 openjdk-8-jdk-headless openjdk-8-jre ubuntu-mono x11-utils x11proto-core-dev x11proto-dev xorg-sgml-doctools xtrans-dev
Suggested packages:
  libasound2-plugins alsa-utils gvfs libice-doc pulseaudio librsvg2-bin lm-sensors libsm-doc libxcb-doc libxt-doc openjdk-8-demo openjdk-8-source visualvm icedtea-8-plugin mesa-utils
The following NEW packages will be installed:
  adwaita-icon-theme at-spi2-core fontconfig fonts-dejavu-extra gtk-update-icon-cache hicolor-icon-theme humanity-icon-theme libasound2 libasound2-data libasyncns0 libatk-bridge2.0-0
  libatk-wrapper-java libatk-wrapper-java-jni libatk1.0-0 libatk1.0-data libatspi2.0-0 libcairo2 libcroco3 libdatrie1 libdrm-amdgpu1 libdrm-intel1 libdrm-nouveau2 libdrm-radeon1 libflac8
  libfontenc1 libgail-common libgail18 libgdk-pixbuf2.0-0 libgdk-pixbuf2.0-bin libgdk-pixbuf2.0-common libgif7 libgl1 libgl1-mesa-dri libgl1-mesa-glx libglapi-mesa libglvnd0 libglx-mesa0
  libglx0 libgraphite2-3 libgtk2.0-0 libgtk2.0-bin libgtk2.0-common libharfbuzz0b libice-dev libice6 libjbig0 libllvm9 libogg0 libpango-1.0-0 libpangocairo-1.0-0 libpangoft2-1.0-0
  libpciaccess0 libpixman-1-0 libpthread-stubs0-dev libpulse0 librsvg2-2 librsvg2-common libsensors4 libsm-dev libsm6 libsndfile1 libthai-data libthai0 libtiff5 libvorbis0a libvorbisenc2
  libx11-dev libx11-doc libx11-xcb1 libxau-dev libxaw7 libxcb-dri2-0 libxcb-dri3-0 libxcb-glx0 libxcb-present0 libxcb-render0 libxcb-shape0 libxcb-shm0 libxcb-sync1 libxcb1-dev
  libxcomposite1 libxcursor1 libxdamage1 libxdmcp-dev libxfixes3 libxft2 libxinerama1 libxmu6 libxpm4 libxrandr2 libxshmfence1 libxt-dev libxt6 libxv1 libxxf86dga1 libxxf86vm1 openjdk-8-jdk
  openjdk-8-jdk-headless openjdk-8-jre ubuntu-mono x11-utils x11proto-core-dev x11proto-dev xorg-sgml-doctools xtrans-dev
The following packages will be upgraded:
  libdrm-common libdrm2
2 upgraded, 105 newly installed, 0 to remove and 71 not upgraded.
Need to get 51.1 MB of archives.
After this operation, 433 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 fontconfig amd64 2.12.6-0ubuntu2 [169 kB]
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libogg0 amd64 1.3.2-1 [17.2 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libice6 amd64 2:1.0.9-2 [40.2 kB]
Get:4 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libsm6 amd64 2:1.2.2-1 [15.8 kB]
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxft2 amd64 2.3.2-1 [36.1 kB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxinerama1 amd64 2:1.1.3-1 [7908 B]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxxf86dga1 amd64 2:1.1.4-1 [13.7 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxxf86vm1 amd64 1:1.1.4-1 [10.6 kB]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-common all 2.4.101-2~18.04.1 [5560 B]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm2 amd64 2.4.101-2~18.04.1 [32.3 kB]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 hicolor-icon-theme all 0.17-2 [9976 B]
Get:12 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libjbig0 amd64 2.1-3.1build1 [26.7 kB]
Get:13 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libtiff5 amd64 4.0.9-5ubuntu0.3 [153 kB]
Get:14 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgdk-pixbuf2.0-common all 2.36.11-2 [4536 B]
Get:15 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgdk-pixbuf2.0-0 amd64 2.36.11-2 [165 kB]
Get:16 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 gtk-update-icon-cache amd64 3.22.30-1ubuntu4 [28.3 kB]
Get:17 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libpixman-1-0 amd64 0.34.0-2 [229 kB]
Get:18 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-render0 amd64 1.13-2~ubuntu18.04 [14.7 kB]
Get:19 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-shm0 amd64 1.13-2~ubuntu18.04 [5600 B]
Get:20 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libcairo2 amd64 1.15.10-2ubuntu0.1 [580 kB]
Get:21 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libcroco3 amd64 0.6.12-2 [81.3 kB]
Get:22 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libthai-data all 0.1.27-2 [133 kB]
Get:23 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libdatrie1 amd64 0.2.10-7 [17.8 kB]
Get:24 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libthai0 amd64 0.1.27-2 [18.0 kB]
Get:25 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libpango-1.0-0 amd64 1.40.14-1ubuntu0.1 [153 kB]
Get:26 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgraphite2-3 amd64 1.3.11-2 [78.7 kB]
Get:27 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libharfbuzz0b amd64 1.7.2-1ubuntu1 [232 kB]
Get:28 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libpangoft2-1.0-0 amd64 1.40.14-1ubuntu0.1 [33.2 kB]
Get:29 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libpangocairo-1.0-0 amd64 1.40.14-1ubuntu0.1 [20.8 kB]
Get:30 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 librsvg2-2 amd64 2.40.20-2 [98.6 kB]
Get:31 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 librsvg2-common amd64 2.40.20-2 [5124 B]
Get:32 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 humanity-icon-theme all 0.6.15 [1250 kB]
Get:33 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 ubuntu-mono all 16.10+18.04.20181005-0ubuntu1 [149 kB]
Get:34 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 adwaita-icon-theme all 3.28.0-1ubuntu1 [3306 kB]
Get:35 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatspi2.0-0 amd64 2.28.0-1 [59.6 kB]
Get:36 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 at-spi2-core amd64 2.28.0-1 [47.9 kB]
Get:37 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 fonts-dejavu-extra all 2.37-1 [1953 kB]
Get:38 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libasound2-data all 1.1.3-5ubuntu0.5 [38.7 kB]
Get:39 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libasound2 amd64 1.1.3-5ubuntu0.5 [360 kB]
Get:40 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libasyncns0 amd64 0.8-6 [12.1 kB]
Get:41 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk1.0-data all 2.28.1-1 [2992 B]
Get:42 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk1.0-0 amd64 2.28.1-1 [43.9 kB]
Get:43 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk-bridge2.0-0 amd64 2.26.2-1 [57.3 kB]
Get:44 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libfontenc1 amd64 1:1.1.3-1 [13.9 kB]
Get:45 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libglvnd0 amd64 1.0.0-2ubuntu2.3 [47.0 kB]
Get:46 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libglapi-mesa amd64 19.2.8-0ubuntu0~18.04.3 [26.5 kB]
Get:47 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libx11-xcb1 amd64 2:1.6.4-3ubuntu0.2 [9376 B]
Get:48 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-dri2-0 amd64 1.13-2~ubuntu18.04 [6920 B]
Get:49 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-dri3-0 amd64 1.13-2~ubuntu18.04 [6568 B]
Get:50 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-glx0 amd64 1.13-2~ubuntu18.04 [22.1 kB]
Get:51 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-present0 amd64 1.13-2~ubuntu18.04 [5552 B]
Get:52 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-sync1 amd64 1.13-2~ubuntu18.04 [8808 B]
Get:53 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxdamage1 amd64 1:1.1.4-3 [6934 B]
Get:54 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxfixes3 amd64 1:5.0.3-1 [10.8 kB]
Get:55 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxshmfence1 amd64 1.3-1 [5028 B]
Get:56 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-amdgpu1 amd64 2.4.101-2~18.04.1 [18.2 kB]
Get:57 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libpciaccess0 amd64 0.14-1 [17.9 kB]
Get:58 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-intel1 amd64 2.4.101-2~18.04.1 [60.0 kB]
Get:59 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-nouveau2 amd64 2.4.101-2~18.04.1 [16.5 kB]
Get:60 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdrm-radeon1 amd64 2.4.101-2~18.04.1 [21.7 kB]
Get:61 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libllvm9 amd64 1:9-2~ubuntu18.04.2 [14.8 MB]
Get:62 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libsensors4 amd64 1:3.4.0-4 [28.8 kB]
Get:63 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgl1-mesa-dri amd64 19.2.8-0ubuntu0~18.04.3 [8811 kB]
Get:64 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libglx-mesa0 amd64 19.2.8-0ubuntu0~18.04.3 [139 kB]
Get:65 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libglx0 amd64 1.0.0-2ubuntu2.3 [28.1 kB]
Get:66 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgl1 amd64 1.0.0-2ubuntu2.3 [86.2 kB]
Get:67 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgl1-mesa-glx amd64 19.2.8-0ubuntu0~18.04.3 [5528 B]
Get:68 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxt6 amd64 1:1.1.5-1 [160 kB]
Get:69 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxmu6 amd64 2:1.1.2-2 [46.0 kB]
Get:70 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxpm4 amd64 1:3.5.12-1 [34.0 kB]
Get:71 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxaw7 amd64 2:1.0.13-1 [173 kB]
Get:72 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb-shape0 amd64 1.13-2~ubuntu18.04 [5972 B]
Get:73 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxcomposite1 amd64 1:0.4.4-2 [6988 B]
Get:74 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxrandr2 amd64 2:1.5.1-1 [18.1 kB]
Get:75 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxv1 amd64 2:1.0.11-1 [10.7 kB]
Get:76 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 x11-utils amd64 7.7+3build1 [196 kB]
Get:77 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk-wrapper-java all 0.33.3-20ubuntu0.1 [34.7 kB]
Get:78 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libatk-wrapper-java-jni amd64 0.33.3-20ubuntu0.1 [28.3 kB]
Get:79 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libflac8 amd64 1.3.2-1 [213 kB]
Get:80 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgtk2.0-common all 2.24.32-1ubuntu1 [125 kB]
Get:81 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxcursor1 amd64 1:1.1.15-1 [19.8 kB]
Get:82 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgtk2.0-0 amd64 2.24.32-1ubuntu1 [1769 kB]
Get:83 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgail18 amd64 2.24.32-1ubuntu1 [14.2 kB]
Get:84 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgail-common amd64 2.24.32-1ubuntu1 [112 kB]
Get:85 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgdk-pixbuf2.0-bin amd64 2.36.11-2 [7864 B]
Get:86 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgif7 amd64 5.1.4-2ubuntu0.1 [30.9 kB]
Get:87 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libgtk2.0-bin amd64 2.24.32-1ubuntu1 [7536 B]
Get:88 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 xorg-sgml-doctools all 1:1.11-1 [12.9 kB]
Get:89 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 x11proto-dev all 2018.4-4 [251 kB]
Get:90 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 x11proto-core-dev all 2018.4-4 [2620 B]
Get:91 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libice-dev amd64 2:1.0.9-2 [46.8 kB]
Get:92 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libpthread-stubs0-dev amd64 0.3-4 [4068 B]
Get:93 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libvorbis0a amd64 1.3.5-4.2 [86.4 kB]
Get:94 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libvorbisenc2 amd64 1.3.5-4.2 [70.7 kB]
Get:95 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libsndfile1 amd64 1.0.28-4ubuntu0.18.04.1 [170 kB]
Get:96 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libpulse0 amd64 1:11.1-1ubuntu7.8 [266 kB]
Get:97 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libsm-dev amd64 2:1.2.2-1 [16.2 kB]
Get:98 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxau-dev amd64 1:1.0.8-1 [11.1 kB]
Get:99 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxdmcp-dev amd64 1:1.1.2-3 [25.1 kB]
Get:100 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 xtrans-dev all 1.3.5-1 [70.5 kB]
Get:101 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libxcb1-dev amd64 1.13-2~ubuntu18.04 [80.0 kB]
Get:102 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libx11-dev amd64 2:1.6.4-3ubuntu0.2 [640 kB]
Get:103 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libx11-doc all 2:1.6.4-3ubuntu0.2 [2065 kB]
Get:104 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/main amd64 libxt-dev amd64 1:1.1.5-1 [395 kB]
Get:105 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 openjdk-8-jre amd64 8u252-b09-1~18.04 [69.8 kB]
Get:106 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 openjdk-8-jdk-headless amd64 8u252-b09-1~18.04 [8250 kB]
Get:107 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 openjdk-8-jdk amd64 8u252-b09-1~18.04 [1622 kB]
Fetched 51.1 MB in 1s (45.6 MB/s)
Extracting templates from packages: 100%
Selecting previously unselected package fontconfig.
(Reading database ... 57076 files and directories currently installed.)
Preparing to unpack .../000-fontconfig_2.12.6-0ubuntu2_amd64.deb ...
Unpacking fontconfig (2.12.6-0ubuntu2) ...
Selecting previously unselected package libogg0:amd64.
Preparing to unpack .../001-libogg0_1.3.2-1_amd64.deb ...
Unpacking libogg0:amd64 (1.3.2-1) ...
Selecting previously unselected package libice6:amd64.
Preparing to unpack .../002-libice6_2%3a1.0.9-2_amd64.deb ...
Unpacking libice6:amd64 (2:1.0.9-2) ...
Selecting previously unselected package libsm6:amd64.
Preparing to unpack .../003-libsm6_2%3a1.2.2-1_amd64.deb ...
Unpacking libsm6:amd64 (2:1.2.2-1) ...
Selecting previously unselected package libxft2:amd64.
Preparing to unpack .../004-libxft2_2.3.2-1_amd64.deb ...
Unpacking libxft2:amd64 (2.3.2-1) ...
Selecting previously unselected package libxinerama1:amd64.
Preparing to unpack .../005-libxinerama1_2%3a1.1.3-1_amd64.deb ...
Unpacking libxinerama1:amd64 (2:1.1.3-1) ...
Selecting previously unselected package libxxf86dga1:amd64.
Preparing to unpack .../006-libxxf86dga1_2%3a1.1.4-1_amd64.deb ...
Unpacking libxxf86dga1:amd64 (2:1.1.4-1) ...
Selecting previously unselected package libxxf86vm1:amd64.
Preparing to unpack .../007-libxxf86vm1_1%3a1.1.4-1_amd64.deb ...
Unpacking libxxf86vm1:amd64 (1:1.1.4-1) ...
Preparing to unpack .../008-libdrm-common_2.4.101-2~18.04.1_all.deb ...
Unpacking libdrm-common (2.4.101-2~18.04.1) over (2.4.99-1ubuntu1~18.04.2) ...
Preparing to unpack .../009-libdrm2_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm2:amd64 (2.4.101-2~18.04.1) over (2.4.99-1ubuntu1~18.04.2) ...
Selecting previously unselected package hicolor-icon-theme.
Preparing to unpack .../010-hicolor-icon-theme_0.17-2_all.deb ...
Unpacking hicolor-icon-theme (0.17-2) ...
Selecting previously unselected package libjbig0:amd64.
Preparing to unpack .../011-libjbig0_2.1-3.1build1_amd64.deb ...
Unpacking libjbig0:amd64 (2.1-3.1build1) ...
Selecting previously unselected package libtiff5:amd64.
Preparing to unpack .../012-libtiff5_4.0.9-5ubuntu0.3_amd64.deb ...
Unpacking libtiff5:amd64 (4.0.9-5ubuntu0.3) ...
Selecting previously unselected package libgdk-pixbuf2.0-common.
Preparing to unpack .../013-libgdk-pixbuf2.0-common_2.36.11-2_all.deb ...
Unpacking libgdk-pixbuf2.0-common (2.36.11-2) ...
Selecting previously unselected package libgdk-pixbuf2.0-0:amd64.
Preparing to unpack .../014-libgdk-pixbuf2.0-0_2.36.11-2_amd64.deb ...
Unpacking libgdk-pixbuf2.0-0:amd64 (2.36.11-2) ...
Selecting previously unselected package gtk-update-icon-cache.
Preparing to unpack .../015-gtk-update-icon-cache_3.22.30-1ubuntu4_amd64.deb ...
No diversion 'diversion of /usr/sbin/update-icon-caches to /usr/sbin/update-icon-caches.gtk2 by libgtk-3-bin', none removed.
No diversion 'diversion of /usr/share/man/man8/update-icon-caches.8.gz to /usr/share/man/man8/update-icon-caches.gtk2.8.gz by libgtk-3-bin', none removed.
Unpacking gtk-update-icon-cache (3.22.30-1ubuntu4) ...
Selecting previously unselected package libpixman-1-0:amd64.
Preparing to unpack .../016-libpixman-1-0_0.34.0-2_amd64.deb ...
Unpacking libpixman-1-0:amd64 (0.34.0-2) ...
Selecting previously unselected package libxcb-render0:amd64.
Preparing to unpack .../017-libxcb-render0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-render0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-shm0:amd64.
Preparing to unpack .../018-libxcb-shm0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-shm0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libcairo2:amd64.
Preparing to unpack .../019-libcairo2_1.15.10-2ubuntu0.1_amd64.deb ...
Unpacking libcairo2:amd64 (1.15.10-2ubuntu0.1) ...
Selecting previously unselected package libcroco3:amd64.
Preparing to unpack .../020-libcroco3_0.6.12-2_amd64.deb ...
Unpacking libcroco3:amd64 (0.6.12-2) ...
Selecting previously unselected package libthai-data.
Preparing to unpack .../021-libthai-data_0.1.27-2_all.deb ...
Unpacking libthai-data (0.1.27-2) ...
Selecting previously unselected package libdatrie1:amd64.
Preparing to unpack .../022-libdatrie1_0.2.10-7_amd64.deb ...
Unpacking libdatrie1:amd64 (0.2.10-7) ...
Selecting previously unselected package libthai0:amd64.
Preparing to unpack .../023-libthai0_0.1.27-2_amd64.deb ...
Unpacking libthai0:amd64 (0.1.27-2) ...
Selecting previously unselected package libpango-1.0-0:amd64.
Preparing to unpack .../024-libpango-1.0-0_1.40.14-1ubuntu0.1_amd64.deb ...
Unpacking libpango-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Selecting previously unselected package libgraphite2-3:amd64.
Preparing to unpack .../025-libgraphite2-3_1.3.11-2_amd64.deb ...
Unpacking libgraphite2-3:amd64 (1.3.11-2) ...
Selecting previously unselected package libharfbuzz0b:amd64.
Preparing to unpack .../026-libharfbuzz0b_1.7.2-1ubuntu1_amd64.deb ...
Unpacking libharfbuzz0b:amd64 (1.7.2-1ubuntu1) ...
Selecting previously unselected package libpangoft2-1.0-0:amd64.
Preparing to unpack .../027-libpangoft2-1.0-0_1.40.14-1ubuntu0.1_amd64.deb ...
Unpacking libpangoft2-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Selecting previously unselected package libpangocairo-1.0-0:amd64.
Preparing to unpack .../028-libpangocairo-1.0-0_1.40.14-1ubuntu0.1_amd64.deb ...
Unpacking libpangocairo-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Selecting previously unselected package librsvg2-2:amd64.
Preparing to unpack .../029-librsvg2-2_2.40.20-2_amd64.deb ...
Unpacking librsvg2-2:amd64 (2.40.20-2) ...
Selecting previously unselected package librsvg2-common:amd64.
Preparing to unpack .../030-librsvg2-common_2.40.20-2_amd64.deb ...
Unpacking librsvg2-common:amd64 (2.40.20-2) ...
Selecting previously unselected package humanity-icon-theme.
Preparing to unpack .../031-humanity-icon-theme_0.6.15_all.deb ...
Unpacking humanity-icon-theme (0.6.15) ...
Selecting previously unselected package ubuntu-mono.
Preparing to unpack .../032-ubuntu-mono_16.10+18.04.20181005-0ubuntu1_all.deb ...
Unpacking ubuntu-mono (16.10+18.04.20181005-0ubuntu1) ...
Selecting previously unselected package adwaita-icon-theme.
Preparing to unpack .../033-adwaita-icon-theme_3.28.0-1ubuntu1_all.deb ...
Unpacking adwaita-icon-theme (3.28.0-1ubuntu1) ...
Selecting previously unselected package libatspi2.0-0:amd64.
Preparing to unpack .../034-libatspi2.0-0_2.28.0-1_amd64.deb ...
Unpacking libatspi2.0-0:amd64 (2.28.0-1) ...
Selecting previously unselected package at-spi2-core.
Preparing to unpack .../035-at-spi2-core_2.28.0-1_amd64.deb ...
Unpacking at-spi2-core (2.28.0-1) ...
Selecting previously unselected package fonts-dejavu-extra.
Preparing to unpack .../036-fonts-dejavu-extra_2.37-1_all.deb ...
Unpacking fonts-dejavu-extra (2.37-1) ...
Selecting previously unselected package libasound2-data.
Preparing to unpack .../037-libasound2-data_1.1.3-5ubuntu0.5_all.deb ...
Unpacking libasound2-data (1.1.3-5ubuntu0.5) ...
Selecting previously unselected package libasound2:amd64.
Preparing to unpack .../038-libasound2_1.1.3-5ubuntu0.5_amd64.deb ...
Unpacking libasound2:amd64 (1.1.3-5ubuntu0.5) ...
Selecting previously unselected package libasyncns0:amd64.
Preparing to unpack .../039-libasyncns0_0.8-6_amd64.deb ...
Unpacking libasyncns0:amd64 (0.8-6) ...
Selecting previously unselected package libatk1.0-data.
Preparing to unpack .../040-libatk1.0-data_2.28.1-1_all.deb ...
Unpacking libatk1.0-data (2.28.1-1) ...
Selecting previously unselected package libatk1.0-0:amd64.
Preparing to unpack .../041-libatk1.0-0_2.28.1-1_amd64.deb ...
Unpacking libatk1.0-0:amd64 (2.28.1-1) ...
Selecting previously unselected package libatk-bridge2.0-0:amd64.
Preparing to unpack .../042-libatk-bridge2.0-0_2.26.2-1_amd64.deb ...
Unpacking libatk-bridge2.0-0:amd64 (2.26.2-1) ...
Selecting previously unselected package libfontenc1:amd64.
Preparing to unpack .../043-libfontenc1_1%3a1.1.3-1_amd64.deb ...
Unpacking libfontenc1:amd64 (1:1.1.3-1) ...
Selecting previously unselected package libglvnd0:amd64.
Preparing to unpack .../044-libglvnd0_1.0.0-2ubuntu2.3_amd64.deb ...
Unpacking libglvnd0:amd64 (1.0.0-2ubuntu2.3) ...
Selecting previously unselected package libglapi-mesa:amd64.
Preparing to unpack .../045-libglapi-mesa_19.2.8-0ubuntu0~18.04.3_amd64.deb ...
Unpacking libglapi-mesa:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Selecting previously unselected package libx11-xcb1:amd64.
Preparing to unpack .../046-libx11-xcb1_2%3a1.6.4-3ubuntu0.2_amd64.deb ...
Unpacking libx11-xcb1:amd64 (2:1.6.4-3ubuntu0.2) ...
Selecting previously unselected package libxcb-dri2-0:amd64.
Preparing to unpack .../047-libxcb-dri2-0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-dri2-0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-dri3-0:amd64.
Preparing to unpack .../048-libxcb-dri3-0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-dri3-0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-glx0:amd64.
Preparing to unpack .../049-libxcb-glx0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-glx0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-present0:amd64.
Preparing to unpack .../050-libxcb-present0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-present0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcb-sync1:amd64.
Preparing to unpack .../051-libxcb-sync1_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-sync1:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxdamage1:amd64.
Preparing to unpack .../052-libxdamage1_1%3a1.1.4-3_amd64.deb ...
Unpacking libxdamage1:amd64 (1:1.1.4-3) ...
Selecting previously unselected package libxfixes3:amd64.
Preparing to unpack .../053-libxfixes3_1%3a5.0.3-1_amd64.deb ...
Unpacking libxfixes3:amd64 (1:5.0.3-1) ...
Selecting previously unselected package libxshmfence1:amd64.
Preparing to unpack .../054-libxshmfence1_1.3-1_amd64.deb ...
Unpacking libxshmfence1:amd64 (1.3-1) ...
Selecting previously unselected package libdrm-amdgpu1:amd64.
Preparing to unpack .../055-libdrm-amdgpu1_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm-amdgpu1:amd64 (2.4.101-2~18.04.1) ...
Selecting previously unselected package libpciaccess0:amd64.
Preparing to unpack .../056-libpciaccess0_0.14-1_amd64.deb ...
Unpacking libpciaccess0:amd64 (0.14-1) ...
Selecting previously unselected package libdrm-intel1:amd64.
Preparing to unpack .../057-libdrm-intel1_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm-intel1:amd64 (2.4.101-2~18.04.1) ...
Selecting previously unselected package libdrm-nouveau2:amd64.
Preparing to unpack .../058-libdrm-nouveau2_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm-nouveau2:amd64 (2.4.101-2~18.04.1) ...
Selecting previously unselected package libdrm-radeon1:amd64.
Preparing to unpack .../059-libdrm-radeon1_2.4.101-2~18.04.1_amd64.deb ...
Unpacking libdrm-radeon1:amd64 (2.4.101-2~18.04.1) ...
Selecting previously unselected package libllvm9:amd64.
Preparing to unpack .../060-libllvm9_1%3a9-2~ubuntu18.04.2_amd64.deb ...
Unpacking libllvm9:amd64 (1:9-2~ubuntu18.04.2) ...
Selecting previously unselected package libsensors4:amd64.
Preparing to unpack .../061-libsensors4_1%3a3.4.0-4_amd64.deb ...
Unpacking libsensors4:amd64 (1:3.4.0-4) ...
Selecting previously unselected package libgl1-mesa-dri:amd64.
Preparing to unpack .../062-libgl1-mesa-dri_19.2.8-0ubuntu0~18.04.3_amd64.deb ...
Unpacking libgl1-mesa-dri:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Selecting previously unselected package libglx-mesa0:amd64.
Preparing to unpack .../063-libglx-mesa0_19.2.8-0ubuntu0~18.04.3_amd64.deb ...
Unpacking libglx-mesa0:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Selecting previously unselected package libglx0:amd64.
Preparing to unpack .../064-libglx0_1.0.0-2ubuntu2.3_amd64.deb ...
Unpacking libglx0:amd64 (1.0.0-2ubuntu2.3) ...
Selecting previously unselected package libgl1:amd64.
Preparing to unpack .../065-libgl1_1.0.0-2ubuntu2.3_amd64.deb ...
Unpacking libgl1:amd64 (1.0.0-2ubuntu2.3) ...
Selecting previously unselected package libgl1-mesa-glx:amd64.
Preparing to unpack .../066-libgl1-mesa-glx_19.2.8-0ubuntu0~18.04.3_amd64.deb ...
Unpacking libgl1-mesa-glx:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Selecting previously unselected package libxt6:amd64.
Preparing to unpack .../067-libxt6_1%3a1.1.5-1_amd64.deb ...
Unpacking libxt6:amd64 (1:1.1.5-1) ...
Selecting previously unselected package libxmu6:amd64.
Preparing to unpack .../068-libxmu6_2%3a1.1.2-2_amd64.deb ...
Unpacking libxmu6:amd64 (2:1.1.2-2) ...
Selecting previously unselected package libxpm4:amd64.
Preparing to unpack .../069-libxpm4_1%3a3.5.12-1_amd64.deb ...
Unpacking libxpm4:amd64 (1:3.5.12-1) ...
Selecting previously unselected package libxaw7:amd64.
Preparing to unpack .../070-libxaw7_2%3a1.0.13-1_amd64.deb ...
Unpacking libxaw7:amd64 (2:1.0.13-1) ...
Selecting previously unselected package libxcb-shape0:amd64.
Preparing to unpack .../071-libxcb-shape0_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb-shape0:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libxcomposite1:amd64.
Preparing to unpack .../072-libxcomposite1_1%3a0.4.4-2_amd64.deb ...
Unpacking libxcomposite1:amd64 (1:0.4.4-2) ...
Selecting previously unselected package libxrandr2:amd64.
Preparing to unpack .../073-libxrandr2_2%3a1.5.1-1_amd64.deb ...
Unpacking libxrandr2:amd64 (2:1.5.1-1) ...
Selecting previously unselected package libxv1:amd64.
Preparing to unpack .../074-libxv1_2%3a1.0.11-1_amd64.deb ...
Unpacking libxv1:amd64 (2:1.0.11-1) ...
Selecting previously unselected package x11-utils.
Preparing to unpack .../075-x11-utils_7.7+3build1_amd64.deb ...
Unpacking x11-utils (7.7+3build1) ...
Selecting previously unselected package libatk-wrapper-java.
Preparing to unpack .../076-libatk-wrapper-java_0.33.3-20ubuntu0.1_all.deb ...
Unpacking libatk-wrapper-java (0.33.3-20ubuntu0.1) ...
Selecting previously unselected package libatk-wrapper-java-jni:amd64.
Preparing to unpack .../077-libatk-wrapper-java-jni_0.33.3-20ubuntu0.1_amd64.deb ...
Unpacking libatk-wrapper-java-jni:amd64 (0.33.3-20ubuntu0.1) ...
Selecting previously unselected package libflac8:amd64.
Preparing to unpack .../078-libflac8_1.3.2-1_amd64.deb ...
Unpacking libflac8:amd64 (1.3.2-1) ...
Selecting previously unselected package libgtk2.0-common.
Preparing to unpack .../079-libgtk2.0-common_2.24.32-1ubuntu1_all.deb ...
Unpacking libgtk2.0-common (2.24.32-1ubuntu1) ...
Selecting previously unselected package libxcursor1:amd64.
Preparing to unpack .../080-libxcursor1_1%3a1.1.15-1_amd64.deb ...
Unpacking libxcursor1:amd64 (1:1.1.15-1) ...
Selecting previously unselected package libgtk2.0-0:amd64.
Preparing to unpack .../081-libgtk2.0-0_2.24.32-1ubuntu1_amd64.deb ...
Unpacking libgtk2.0-0:amd64 (2.24.32-1ubuntu1) ...
Selecting previously unselected package libgail18:amd64.
Preparing to unpack .../082-libgail18_2.24.32-1ubuntu1_amd64.deb ...
Unpacking libgail18:amd64 (2.24.32-1ubuntu1) ...
Selecting previously unselected package libgail-common:amd64.
Preparing to unpack .../083-libgail-common_2.24.32-1ubuntu1_amd64.deb ...
Unpacking libgail-common:amd64 (2.24.32-1ubuntu1) ...
Selecting previously unselected package libgdk-pixbuf2.0-bin.
Preparing to unpack .../084-libgdk-pixbuf2.0-bin_2.36.11-2_amd64.deb ...
Unpacking libgdk-pixbuf2.0-bin (2.36.11-2) ...
Selecting previously unselected package libgif7:amd64.
Preparing to unpack .../085-libgif7_5.1.4-2ubuntu0.1_amd64.deb ...
Unpacking libgif7:amd64 (5.1.4-2ubuntu0.1) ...
Selecting previously unselected package libgtk2.0-bin.
Preparing to unpack .../086-libgtk2.0-bin_2.24.32-1ubuntu1_amd64.deb ...
Unpacking libgtk2.0-bin (2.24.32-1ubuntu1) ...
Selecting previously unselected package xorg-sgml-doctools.
Preparing to unpack .../087-xorg-sgml-doctools_1%3a1.11-1_all.deb ...
Unpacking xorg-sgml-doctools (1:1.11-1) ...
Selecting previously unselected package x11proto-dev.
Preparing to unpack .../088-x11proto-dev_2018.4-4_all.deb ...
Unpacking x11proto-dev (2018.4-4) ...
Selecting previously unselected package x11proto-core-dev.
Preparing to unpack .../089-x11proto-core-dev_2018.4-4_all.deb ...
Unpacking x11proto-core-dev (2018.4-4) ...
Selecting previously unselected package libice-dev:amd64.
Preparing to unpack .../090-libice-dev_2%3a1.0.9-2_amd64.deb ...
Unpacking libice-dev:amd64 (2:1.0.9-2) ...
Selecting previously unselected package libpthread-stubs0-dev:amd64.
Preparing to unpack .../091-libpthread-stubs0-dev_0.3-4_amd64.deb ...
Unpacking libpthread-stubs0-dev:amd64 (0.3-4) ...
Selecting previously unselected package libvorbis0a:amd64.
Preparing to unpack .../092-libvorbis0a_1.3.5-4.2_amd64.deb ...
Unpacking libvorbis0a:amd64 (1.3.5-4.2) ...
Selecting previously unselected package libvorbisenc2:amd64.
Preparing to unpack .../093-libvorbisenc2_1.3.5-4.2_amd64.deb ...
Unpacking libvorbisenc2:amd64 (1.3.5-4.2) ...
Selecting previously unselected package libsndfile1:amd64.
Preparing to unpack .../094-libsndfile1_1.0.28-4ubuntu0.18.04.1_amd64.deb ...
Unpacking libsndfile1:amd64 (1.0.28-4ubuntu0.18.04.1) ...
Selecting previously unselected package libpulse0:amd64.
Preparing to unpack .../095-libpulse0_1%3a11.1-1ubuntu7.8_amd64.deb ...
Unpacking libpulse0:amd64 (1:11.1-1ubuntu7.8) ...
Selecting previously unselected package libsm-dev:amd64.
Preparing to unpack .../096-libsm-dev_2%3a1.2.2-1_amd64.deb ...
Unpacking libsm-dev:amd64 (2:1.2.2-1) ...
Selecting previously unselected package libxau-dev:amd64.
Preparing to unpack .../097-libxau-dev_1%3a1.0.8-1_amd64.deb ...
Unpacking libxau-dev:amd64 (1:1.0.8-1) ...
Selecting previously unselected package libxdmcp-dev:amd64.
Preparing to unpack .../098-libxdmcp-dev_1%3a1.1.2-3_amd64.deb ...
Unpacking libxdmcp-dev:amd64 (1:1.1.2-3) ...
Selecting previously unselected package xtrans-dev.
Preparing to unpack .../099-xtrans-dev_1.3.5-1_all.deb ...
Unpacking xtrans-dev (1.3.5-1) ...
Selecting previously unselected package libxcb1-dev:amd64.
Preparing to unpack .../100-libxcb1-dev_1.13-2~ubuntu18.04_amd64.deb ...
Unpacking libxcb1-dev:amd64 (1.13-2~ubuntu18.04) ...
Selecting previously unselected package libx11-dev:amd64.
Preparing to unpack .../101-libx11-dev_2%3a1.6.4-3ubuntu0.2_amd64.deb ...
Unpacking libx11-dev:amd64 (2:1.6.4-3ubuntu0.2) ...
Selecting previously unselected package libx11-doc.
Preparing to unpack .../102-libx11-doc_2%3a1.6.4-3ubuntu0.2_all.deb ...
Unpacking libx11-doc (2:1.6.4-3ubuntu0.2) ...
Selecting previously unselected package libxt-dev:amd64.
Preparing to unpack .../103-libxt-dev_1%3a1.1.5-1_amd64.deb ...
Unpacking libxt-dev:amd64 (1:1.1.5-1) ...
Selecting previously unselected package openjdk-8-jre:amd64.
Preparing to unpack .../104-openjdk-8-jre_8u252-b09-1~18.04_amd64.deb ...
Unpacking openjdk-8-jre:amd64 (8u252-b09-1~18.04) ...
Selecting previously unselected package openjdk-8-jdk-headless:amd64.
Preparing to unpack .../105-openjdk-8-jdk-headless_8u252-b09-1~18.04_amd64.deb ...
Unpacking openjdk-8-jdk-headless:amd64 (8u252-b09-1~18.04) ...
Selecting previously unselected package openjdk-8-jdk:amd64.
Preparing to unpack .../106-openjdk-8-jdk_8u252-b09-1~18.04_amd64.deb ...
Unpacking openjdk-8-jdk:amd64 (8u252-b09-1~18.04) ...
Setting up libxcb-present0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libglvnd0:amd64 (1.0.0-2ubuntu2.3) ...
Setting up libxinerama1:amd64 (2:1.1.3-1) ...
Setting up libxcb-dri2-0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libxcb-dri3-0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libxcb-glx0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libgtk2.0-common (2.24.32-1ubuntu1) ...
Setting up libxcb-render0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libasyncns0:amd64 (0.8-6) ...
Setting up libxdamage1:amd64 (1:1.1.4-3) ...
Setting up libxfixes3:amd64 (1:5.0.3-1) ...
Setting up libjbig0:amd64 (2.1-3.1build1) ...
Setting up libpthread-stubs0-dev:amd64 (0.3-4) ...
Setting up openjdk-8-jdk-headless:amd64 (8u252-b09-1~18.04) ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/idlj to provide /usr/bin/idlj (idlj) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jdeps to provide /usr/bin/jdeps (jdeps) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/wsimport to provide /usr/bin/wsimport (wsimport) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/rmic to provide /usr/bin/rmic (rmic) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jinfo to provide /usr/bin/jinfo (jinfo) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jsadebugd to provide /usr/bin/jsadebugd (jsadebugd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/native2ascii to provide /usr/bin/native2ascii (native2ascii) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jstat to provide /usr/bin/jstat (jstat) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javadoc to provide /usr/bin/javadoc (javadoc) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javah to provide /usr/bin/javah (javah) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/clhsdb to provide /usr/bin/clhsdb (clhsdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jstack to provide /usr/bin/jstack (jstack) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jrunscript to provide /usr/bin/jrunscript (jrunscript) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javac to provide /usr/bin/javac (javac) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javap to provide /usr/bin/javap (javap) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jar to provide /usr/bin/jar (jar) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/extcheck to provide /usr/bin/extcheck (extcheck) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/hsdb to provide /usr/bin/hsdb (hsdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/schemagen to provide /usr/bin/schemagen (schemagen) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jps to provide /usr/bin/jps (jps) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/xjc to provide /usr/bin/xjc (xjc) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jmap to provide /usr/bin/jmap (jmap) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jstatd to provide /usr/bin/jstatd (jstatd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jhat to provide /usr/bin/jhat (jhat) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jdb to provide /usr/bin/jdb (jdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/serialver to provide /usr/bin/serialver (serialver) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/wsgen to provide /usr/bin/wsgen (wsgen) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jcmd to provide /usr/bin/jcmd (jcmd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jarsigner to provide /usr/bin/jarsigner (jarsigner) in auto mode
Setting up libatspi2.0-0:amd64 (2.28.0-1) ...
Setting up at-spi2-core (2.28.0-1) ...
Setting up libasound2-data (1.1.3-5ubuntu0.5) ...
Setting up libxshmfence1:amd64 (1.3-1) ...
Setting up xorg-sgml-doctools (1:1.11-1) ...
Setting up libgdk-pixbuf2.0-common (2.36.11-2) ...
Setting up libdatrie1:amd64 (0.2.10-7) ...
Setting up libtiff5:amd64 (4.0.9-5ubuntu0.3) ...
Setting up libgif7:amd64 (5.1.4-2ubuntu0.1) ...
Setting up libglapi-mesa:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Setting up x11proto-dev (2018.4-4) ...
Setting up libasound2:amd64 (1.1.3-5ubuntu0.5) ...
Setting up libdrm-common (2.4.101-2~18.04.1) ...
Setting up libgraphite2-3:amd64 (1.3.11-2) ...
Setting up libcroco3:amd64 (0.6.12-2) ...
Setting up libxcb-sync1:amd64 (1.13-2~ubuntu18.04) ...
Setting up libogg0:amd64 (1.3.2-1) ...
Setting up libatk1.0-data (2.28.1-1) ...
Setting up libx11-xcb1:amd64 (2:1.6.4-3ubuntu0.2) ...
Setting up libpixman-1-0:amd64 (0.34.0-2) ...
Setting up xtrans-dev (1.3.5-1) ...
Setting up libxcursor1:amd64 (1:1.1.15-1) ...
Setting up libxdmcp-dev:amd64 (1:1.1.2-3) ...
Setting up libxxf86dga1:amd64 (2:1.1.4-1) ...
Setting up libatk1.0-0:amd64 (2.28.1-1) ...
Setting up libatk-bridge2.0-0:amd64 (2.26.2-1) ...
Setting up libice6:amd64 (2:1.0.9-2) ...
Setting up libfontenc1:amd64 (1:1.1.3-1) ...
Setting up libxcomposite1:amd64 (1:0.4.4-2) ...
Setting up libxcb-shm0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libxpm4:amd64 (1:3.5.12-1) ...
Setting up libx11-doc (2:1.6.4-3ubuntu0.2) ...
Setting up libxcb-shape0:amd64 (1.13-2~ubuntu18.04) ...
Setting up libpciaccess0:amd64 (0.14-1) ...
Setting up libxv1:amd64 (2:1.0.11-1) ...
Setting up libsensors4:amd64 (1:3.4.0-4) ...
Setting up libthai-data (0.1.27-2) ...
Setting up libxxf86vm1:amd64 (1:1.1.4-1) ...
Setting up libllvm9:amd64 (1:9-2~ubuntu18.04.2) ...
Setting up libxft2:amd64 (2.3.2-1) ...
Setting up fonts-dejavu-extra (2.37-1) ...
Setting up libvorbis0a:amd64 (1.3.5-4.2) ...
Setting up hicolor-icon-theme (0.17-2) ...
Setting up libxrandr2:amd64 (2:1.5.1-1) ...
Setting up fontconfig (2.12.6-0ubuntu2) ...
Regenerating fonts cache... done.
Setting up libcairo2:amd64 (1.15.10-2ubuntu0.1) ...
Setting up libsm6:amd64 (2:1.2.2-1) ...
Setting up x11proto-core-dev (2018.4-4) ...
Setting up libgdk-pixbuf2.0-0:amd64 (2.36.11-2) ...
Setting up libflac8:amd64 (1.3.2-1) ...
Setting up libgdk-pixbuf2.0-bin (2.36.11-2) ...
Setting up libharfbuzz0b:amd64 (1.7.2-1ubuntu1) ...
Setting up libxau-dev:amd64 (1:1.0.8-1) ...
Setting up libthai0:amd64 (0.1.27-2) ...
Setting up libdrm2:amd64 (2.4.101-2~18.04.1) ...
Setting up libdrm-intel1:amd64 (2.4.101-2~18.04.1) ...
Setting up gtk-update-icon-cache (3.22.30-1ubuntu4) ...
Setting up libice-dev:amd64 (2:1.0.9-2) ...
Setting up libpango-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Setting up libxt6:amd64 (1:1.1.5-1) ...
Setting up libxcb1-dev:amd64 (1.13-2~ubuntu18.04) ...
Setting up libdrm-radeon1:amd64 (2.4.101-2~18.04.1) ...
Setting up libx11-dev:amd64 (2:1.6.4-3ubuntu0.2) ...
Setting up libvorbisenc2:amd64 (1.3.5-4.2) ...
Setting up libdrm-nouveau2:amd64 (2.4.101-2~18.04.1) ...
Setting up libsm-dev:amd64 (2:1.2.2-1) ...
Setting up libdrm-amdgpu1:amd64 (2.4.101-2~18.04.1) ...
Setting up libgl1-mesa-dri:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Setting up libxmu6:amd64 (2:1.1.2-2) ...
Setting up libpangoft2-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Setting up libsndfile1:amd64 (1.0.28-4ubuntu0.18.04.1) ...
Setting up libglx-mesa0:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Setting up libxaw7:amd64 (2:1.0.13-1) ...
Setting up libxt-dev:amd64 (1:1.1.5-1) ...
Setting up libpangocairo-1.0-0:amd64 (1.40.14-1ubuntu0.1) ...
Setting up libpulse0:amd64 (1:11.1-1ubuntu7.8) ...
Setting up libglx0:amd64 (1.0.0-2ubuntu2.3) ...
Setting up librsvg2-2:amd64 (2.40.20-2) ...
Setting up librsvg2-common:amd64 (2.40.20-2) ...
Setting up libgl1:amd64 (1.0.0-2ubuntu2.3) ...
Setting up x11-utils (7.7+3build1) ...
Setting up libgl1-mesa-glx:amd64 (19.2.8-0ubuntu0~18.04.3) ...
Setting up libatk-wrapper-java (0.33.3-20ubuntu0.1) ...
Setting up libatk-wrapper-java-jni:amd64 (0.33.3-20ubuntu0.1) ...
Setting up adwaita-icon-theme (3.28.0-1ubuntu1) ...
update-alternatives: using /usr/share/icons/Adwaita/cursor.theme to provide /usr/share/icons/default/index.theme (x-cursor-theme) in auto mode
Setting up libgtk2.0-0:amd64 (2.24.32-1ubuntu1) ...
Setting up libgail18:amd64 (2.24.32-1ubuntu1) ...
Setting up libgail-common:amd64 (2.24.32-1ubuntu1) ...
Setting up humanity-icon-theme (0.6.15) ...
Setting up openjdk-8-jre:amd64 (8u252-b09-1~18.04) ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/policytool to provide /usr/bin/policytool (policytool) in auto mode
Setting up libgtk2.0-bin (2.24.32-1ubuntu1) ...
Setting up openjdk-8-jdk:amd64 (8u252-b09-1~18.04) ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/appletviewer to provide /usr/bin/appletviewer (appletviewer) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jconsole to provide /usr/bin/jconsole (jconsole) in auto mode
Setting up ubuntu-mono (16.10+18.04.20181005-0ubuntu1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Processing triggers for libgdk-pixbuf2.0-0:amd64 (2.36.11-2) ...
ubuntu@ip-172-31-16-80:~$ export JAVA_HOME=/usr/lib/jvm/java-8-openjdk
ubuntu@ip-172-31-16-80:~$ export PATH=$PATH:/usr/lib/jvm/java-8-openjdk/bin
ubuntu@ip-172-31-16-80:~$ javac -version
javac 1.8.0_252
ubuntu@ip-172-31-16-80:~$ sudo apt update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:4 http://security.ubuntu.com/ubuntu bionic-security InRelease
Hit:5 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic InRelease
Reading package lists... Done
Building dependency tree
Reading state information... Done
71 packages can be upgraded. Run 'apt list --upgradable' to see them.
ubuntu@ip-172-31-16-80:~$ sudo apt install maven
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  libaopalliance-java libapache-pom-java libatinject-jsr330-api-java libcdi-api-java libcommons-cli-java libcommons-io-java libcommons-lang3-java libcommons-parent-java
  libgeronimo-annotation-1.3-spec-java libgeronimo-interceptor-3.0-spec-java libguava-java libguice-java libhawtjni-runtime-java libjansi-java libjansi-native-java libjsr305-java
  libmaven-parent-java libmaven-resolver-java libmaven-shared-utils-java libmaven3-core-java libplexus-cipher-java libplexus-classworlds-java libplexus-component-annotations-java
  libplexus-interpolation-java libplexus-sec-dispatcher-java libplexus-utils2-java libsisu-inject-java libsisu-plexus-java libslf4j-java libwagon-file-java libwagon-http-shaded-java
  libwagon-provider-api-java
Suggested packages:
  libaopalliance-java-doc libatinject-jsr330-api-java-doc libservlet3.1-java libcommons-io-java-doc libcommons-lang3-java-doc libasm-java libcglib-java libjsr305-java-doc
  libmaven-shared-utils-java-doc liblogback-java libplexus-cipher-java-doc libplexus-classworlds-java-doc libplexus-interpolation-java-doc libplexus-sec-dispatcher-java-doc
  libplexus-utils2-java-doc junit4 testng libcommons-logging-java liblog4j1.2-java
The following NEW packages will be installed:
  libaopalliance-java libapache-pom-java libatinject-jsr330-api-java libcdi-api-java libcommons-cli-java libcommons-io-java libcommons-lang3-java libcommons-parent-java
  libgeronimo-annotation-1.3-spec-java libgeronimo-interceptor-3.0-spec-java libguava-java libguice-java libhawtjni-runtime-java libjansi-java libjansi-native-java libjsr305-java
  libmaven-parent-java libmaven-resolver-java libmaven-shared-utils-java libmaven3-core-java libplexus-cipher-java libplexus-classworlds-java libplexus-component-annotations-java
  libplexus-interpolation-java libplexus-sec-dispatcher-java libplexus-utils2-java libsisu-inject-java libsisu-plexus-java libslf4j-java libwagon-file-java libwagon-http-shaded-java
  libwagon-provider-api-java maven
0 upgraded, 33 newly installed, 0 to remove and 71 not upgraded.
Need to get 8916 kB of archives.
After this operation, 11.8 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libapache-pom-java all 18-1 [4720 B]
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libatinject-jsr330-api-java all 1.0+ds1-5 [5348 B]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libgeronimo-interceptor-3.0-spec-java all 1.0.1-4fakesync [8616 B]
Get:4 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libcdi-api-java all 1.2-2 [54.5 kB]
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libcommons-cli-java all 1.4-1 [53.8 kB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libcommons-parent-java all 43-1 [10.8 kB]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libcommons-io-java all 2.6-2 [198 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 libcommons-lang3-java all 3.8-1~18.04.2 [479 kB]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libgeronimo-annotation-1.3-spec-java all 1.0-1 [10.7 kB]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libjsr305-java all 0.1~+svn49-10 [26.5 kB]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libguava-java all 19.0-1 [2028 kB]
Get:12 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libaopalliance-java all 20070526-6 [9084 B]
Get:13 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libguice-java all 4.0-4 [853 kB]
Get:14 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libhawtjni-runtime-java all 1.15-2 [27.1 kB]
Get:15 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libjansi-native-java all 1.7-1 [19.4 kB]
Get:16 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libjansi-java all 1.16-1 [36.2 kB]
Get:17 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 libmaven-parent-java all 31-2~18.04 [5196 B]
Get:18 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libplexus-utils2-java all 3.0.24-3 [246 kB]
Get:19 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libwagon-provider-api-java all 3.0.0-2 [48.2 kB]
Get:20 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 libmaven-resolver-java all 1.3.1-1~18.04 [549 kB]
Get:21 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 libmaven-shared-utils-java all 3.3.0-1~18.04 [149 kB]
Get:22 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libplexus-cipher-java all 1.7-3 [15.1 kB]
Get:23 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libplexus-classworlds-java all 2.5.2-2 [49.3 kB]
Get:24 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libplexus-component-annotations-java all 1.7.1-7 [6596 B]
Get:25 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libplexus-interpolation-java all 1.24-1 [73.4 kB]
Get:26 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libplexus-sec-dispatcher-java all 1.4-3 [28.0 kB]
Get:27 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libslf4j-java all 1.7.25-3 [141 kB]
Get:28 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libsisu-inject-java all 0.3.2-2 [346 kB]
Get:29 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libsisu-plexus-java all 0.3.3-3 [182 kB]
Get:30 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 libmaven3-core-java all 3.6.0-1~18.04.1 [1465 kB]
Get:31 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libwagon-file-java all 3.0.0-2 [7960 B]
Get:32 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 libwagon-http-shaded-java all 3.0.0-2 [1757 kB]
Get:33 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 maven all 3.6.0-1~18.04.1 [22.4 kB]
Fetched 8916 kB in 0s (24.9 MB/s)
Extracting templates from packages: 100%
Selecting previously unselected package libapache-pom-java.
(Reading database ... 72591 files and directories currently installed.)
Preparing to unpack .../00-libapache-pom-java_18-1_all.deb ...
Unpacking libapache-pom-java (18-1) ...
Selecting previously unselected package libatinject-jsr330-api-java.
Preparing to unpack .../01-libatinject-jsr330-api-java_1.0+ds1-5_all.deb ...
Unpacking libatinject-jsr330-api-java (1.0+ds1-5) ...
Selecting previously unselected package libgeronimo-interceptor-3.0-spec-java.
Preparing to unpack .../02-libgeronimo-interceptor-3.0-spec-java_1.0.1-4fakesync_all.deb ...
Unpacking libgeronimo-interceptor-3.0-spec-java (1.0.1-4fakesync) ...
Selecting previously unselected package libcdi-api-java.
Preparing to unpack .../03-libcdi-api-java_1.2-2_all.deb ...
Unpacking libcdi-api-java (1.2-2) ...
Selecting previously unselected package libcommons-cli-java.
Preparing to unpack .../04-libcommons-cli-java_1.4-1_all.deb ...
Unpacking libcommons-cli-java (1.4-1) ...
Selecting previously unselected package libcommons-parent-java.
Preparing to unpack .../05-libcommons-parent-java_43-1_all.deb ...
Unpacking libcommons-parent-java (43-1) ...
Selecting previously unselected package libcommons-io-java.
Preparing to unpack .../06-libcommons-io-java_2.6-2_all.deb ...
Unpacking libcommons-io-java (2.6-2) ...
Selecting previously unselected package libcommons-lang3-java.
Preparing to unpack .../07-libcommons-lang3-java_3.8-1~18.04.2_all.deb ...
Unpacking libcommons-lang3-java (3.8-1~18.04.2) ...
Selecting previously unselected package libgeronimo-annotation-1.3-spec-java.
Preparing to unpack .../08-libgeronimo-annotation-1.3-spec-java_1.0-1_all.deb ...
Unpacking libgeronimo-annotation-1.3-spec-java (1.0-1) ...
Selecting previously unselected package libjsr305-java.
Preparing to unpack .../09-libjsr305-java_0.1~+svn49-10_all.deb ...
Unpacking libjsr305-java (0.1~+svn49-10) ...
Selecting previously unselected package libguava-java.
Preparing to unpack .../10-libguava-java_19.0-1_all.deb ...
Unpacking libguava-java (19.0-1) ...
Selecting previously unselected package libaopalliance-java.
Preparing to unpack .../11-libaopalliance-java_20070526-6_all.deb ...
Unpacking libaopalliance-java (20070526-6) ...
Selecting previously unselected package libguice-java.
Preparing to unpack .../12-libguice-java_4.0-4_all.deb ...
Unpacking libguice-java (4.0-4) ...
Selecting previously unselected package libhawtjni-runtime-java.
Preparing to unpack .../13-libhawtjni-runtime-java_1.15-2_all.deb ...
Unpacking libhawtjni-runtime-java (1.15-2) ...
Selecting previously unselected package libjansi-native-java.
Preparing to unpack .../14-libjansi-native-java_1.7-1_all.deb ...
Unpacking libjansi-native-java (1.7-1) ...
Selecting previously unselected package libjansi-java.
Preparing to unpack .../15-libjansi-java_1.16-1_all.deb ...
Unpacking libjansi-java (1.16-1) ...
Selecting previously unselected package libmaven-parent-java.
Preparing to unpack .../16-libmaven-parent-java_31-2~18.04_all.deb ...
Unpacking libmaven-parent-java (31-2~18.04) ...
Selecting previously unselected package libplexus-utils2-java.
Preparing to unpack .../17-libplexus-utils2-java_3.0.24-3_all.deb ...
Unpacking libplexus-utils2-java (3.0.24-3) ...
Selecting previously unselected package libwagon-provider-api-java.
Preparing to unpack .../18-libwagon-provider-api-java_3.0.0-2_all.deb ...
Unpacking libwagon-provider-api-java (3.0.0-2) ...
Selecting previously unselected package libmaven-resolver-java.
Preparing to unpack .../19-libmaven-resolver-java_1.3.1-1~18.04_all.deb ...
Unpacking libmaven-resolver-java (1.3.1-1~18.04) ...
Selecting previously unselected package libmaven-shared-utils-java.
Preparing to unpack .../20-libmaven-shared-utils-java_3.3.0-1~18.04_all.deb ...
Unpacking libmaven-shared-utils-java (3.3.0-1~18.04) ...
Selecting previously unselected package libplexus-cipher-java.
Preparing to unpack .../21-libplexus-cipher-java_1.7-3_all.deb ...
Unpacking libplexus-cipher-java (1.7-3) ...
Selecting previously unselected package libplexus-classworlds-java.
Preparing to unpack .../22-libplexus-classworlds-java_2.5.2-2_all.deb ...
Unpacking libplexus-classworlds-java (2.5.2-2) ...
Selecting previously unselected package libplexus-component-annotations-java.
Preparing to unpack .../23-libplexus-component-annotations-java_1.7.1-7_all.deb ...
Unpacking libplexus-component-annotations-java (1.7.1-7) ...
Selecting previously unselected package libplexus-interpolation-java.
Preparing to unpack .../24-libplexus-interpolation-java_1.24-1_all.deb ...
Unpacking libplexus-interpolation-java (1.24-1) ...
Selecting previously unselected package libplexus-sec-dispatcher-java.
Preparing to unpack .../25-libplexus-sec-dispatcher-java_1.4-3_all.deb ...
Unpacking libplexus-sec-dispatcher-java (1.4-3) ...
Selecting previously unselected package libslf4j-java.
Preparing to unpack .../26-libslf4j-java_1.7.25-3_all.deb ...
Unpacking libslf4j-java (1.7.25-3) ...
Selecting previously unselected package libsisu-inject-java.
Preparing to unpack .../27-libsisu-inject-java_0.3.2-2_all.deb ...
Unpacking libsisu-inject-java (0.3.2-2) ...
Selecting previously unselected package libsisu-plexus-java.
Preparing to unpack .../28-libsisu-plexus-java_0.3.3-3_all.deb ...
Unpacking libsisu-plexus-java (0.3.3-3) ...
Selecting previously unselected package libmaven3-core-java.
Preparing to unpack .../29-libmaven3-core-java_3.6.0-1~18.04.1_all.deb ...
Unpacking libmaven3-core-java (3.6.0-1~18.04.1) ...
Selecting previously unselected package libwagon-file-java.
Preparing to unpack .../30-libwagon-file-java_3.0.0-2_all.deb ...
Unpacking libwagon-file-java (3.0.0-2) ...
Selecting previously unselected package libwagon-http-shaded-java.
Preparing to unpack .../31-libwagon-http-shaded-java_3.0.0-2_all.deb ...
Unpacking libwagon-http-shaded-java (3.0.0-2) ...
Selecting previously unselected package maven.
Preparing to unpack .../32-maven_3.6.0-1~18.04.1_all.deb ...
Unpacking maven (3.6.0-1~18.04.1) ...
Setting up libslf4j-java (1.7.25-3) ...
Setting up libplexus-classworlds-java (2.5.2-2) ...
Setting up libhawtjni-runtime-java (1.15-2) ...
Setting up libplexus-cipher-java (1.7-3) ...
Setting up libplexus-interpolation-java (1.24-1) ...
Setting up libplexus-component-annotations-java (1.7.1-7) ...
Setting up libplexus-utils2-java (3.0.24-3) ...
Setting up libwagon-provider-api-java (3.0.0-2) ...
Setting up libjsr305-java (0.1~+svn49-10) ...
Setting up libgeronimo-interceptor-3.0-spec-java (1.0.1-4fakesync) ...
Setting up libmaven-resolver-java (1.3.1-1~18.04) ...
Setting up libjansi-native-java (1.7-1) ...
Setting up libwagon-http-shaded-java (3.0.0-2) ...
Setting up libapache-pom-java (18-1) ...
Setting up libatinject-jsr330-api-java (1.0+ds1-5) ...
Setting up libmaven-parent-java (31-2~18.04) ...
Setting up libaopalliance-java (20070526-6) ...
Setting up libgeronimo-annotation-1.3-spec-java (1.0-1) ...
Setting up libcommons-cli-java (1.4-1) ...
Setting up libplexus-sec-dispatcher-java (1.4-3) ...
Setting up libjansi-java (1.16-1) ...
Setting up libguava-java (19.0-1) ...
Setting up libwagon-file-java (3.0.0-2) ...
Setting up libcommons-parent-java (43-1) ...
Setting up libcdi-api-java (1.2-2) ...
Setting up libcommons-lang3-java (3.8-1~18.04.2) ...
Setting up libcommons-io-java (2.6-2) ...
Setting up libguice-java (4.0-4) ...
Setting up libmaven-shared-utils-java (3.3.0-1~18.04) ...
Setting up libsisu-inject-java (0.3.2-2) ...
Setting up libsisu-plexus-java (0.3.3-3) ...
Setting up libmaven3-core-java (3.6.0-1~18.04.1) ...
Setting up maven (3.6.0-1~18.04.1) ...
update-alternatives: using /usr/share/maven/bin/mvn to provide /usr/bin/mvn (mvn) in auto mode
ubuntu@ip-172-31-16-80:~$ mvn -version
The JAVA_HOME environment variable is not defined correctly
This environment variable is needed to run this program
NB: JAVA_HOME should point to a JDK not a JRE
ubuntu@ip-172-31-16-80:~$ export JAVA_HOME=/usr/lib/jvm/java-8-openjdk
ubuntu@ip-172-31-16-80:~$ export JAVA_HOME=/usr/lib/jvm/default-java
ubuntu@ip-172-31-16-80:~$ export M2_HOME=/opt/maven
ubuntu@ip-172-31-16-80:~$ export MAVEN_HOME=/opt/maven
ubuntu@ip-172-31-16-80:~$ export MAVEN_HOME=/opt/maven
ubuntu@ip-172-31-16-80:~$ export PATH=${M2_HOME}/bin:${PATH}
ubuntu@ip-172-31-16-80:~$ maven -version

Command 'maven' not found, did you mean:

  command 'aven' from deb survex-aven
  command 'raven' from deb python3-raven

Try: sudo apt install <deb name>

ubuntu@ip-172-31-16-80:~$ mvn -version
The JAVA_HOME environment variable is not defined correctly
This environment variable is needed to run this program
NB: JAVA_HOME should point to a JDK not a JRE
ubuntu@ip-172-31-16-80:~$ wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz -P /tmp
--2020-06-19 18:58:13--  https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
Resolving www-us.apache.org (www-us.apache.org)... 40.79.78.1
Connecting to www-us.apache.org (www-us.apache.org)|40.79.78.1|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://downloads.apache.org/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz [following]
--2020-06-19 18:58:13--  https://downloads.apache.org/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
Resolving downloads.apache.org (downloads.apache.org)... 88.99.95.219, 2a01:4f8:10a:201a::2
Connecting to downloads.apache.org (downloads.apache.org)|88.99.95.219|:443... connected.
HTTP request sent, awaiting response... 404 Not Found
2020-06-19 18:58:13 ERROR 404: Not Found.

ubuntu@ip-172-31-16-80:~$ sudo apt-get updatea
E: Invalid operation updatea
ubuntu@ip-172-31-16-80:~$ sudo apt-get update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:4 http://security.ubuntu.com/ubuntu bionic-security InRelease
Hit:5 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic InRelease
Reading package lists... Done
ubuntu@ip-172-31-16-80:~$ mvn -version
The JAVA_HOME environment variable is not defined correctly
This environment variable is needed to run this program
NB: JAVA_HOME should point to a JDK not a JRE
ubuntu@ip-172-31-16-80:~$ wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz -P /tmp
--2020-06-19 18:59:18--  https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
Resolving www-us.apache.org (www-us.apache.org)... 40.79.78.1
Connecting to www-us.apache.org (www-us.apache.org)|40.79.78.1|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://downloads.apache.org/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz [following]
--2020-06-19 18:59:18--  https://downloads.apache.org/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
Resolving downloads.apache.org (downloads.apache.org)... 88.99.95.219, 2a01:4f8:10a:201a::2
Connecting to downloads.apache.org (downloads.apache.org)|88.99.95.219|:443... connected.
HTTP request sent, awaiting response... 404 Not Found
2020-06-19 18:59:19 ERROR 404: Not Found.

ubuntu@ip-172-31-16-80:~$ sudo apt-get update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
Hit:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease
Hit:4 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu bionic InRelease
Hit:5 http://security.ubuntu.com/ubuntu bionic-security InRelease
Reading package lists... Done
ubuntu@ip-172-31-16-80:~$ mvn -version
The JAVA_HOME environment variable is not defined correctly
This environment variable is needed to run this program
NB: JAVA_HOME should point to a JDK not a JRE
ubuntu@ip-172-31-16-80:~$ JAVA_HOME="/usr/lib/jvm/java-8-openjdk"
ubuntu@ip-172-31-16-80:~$ mvn -version
The JAVA_HOME environment variable is not defined correctly
This environment variable is needed to run this program
NB: JAVA_HOME should point to a JDK not a JRE
ubuntu@ip-172-31-16-80:~$ echo $JAVA_HOME
/usr/lib/jvm/java-8-openjdk
ubuntu@ip-172-31-16-80:~$ cd /usr/lib/jvm/java-8-openjdk
-bash: cd: /usr/lib/jvm/java-8-openjdk: No such file or directory
ubuntu@ip-172-31-16-80:~$ ls
ubuntu@ip-172-31-16-80:~$ cd /usr/lib/jvm/
ubuntu@ip-172-31-16-80:/usr/lib/jvm$ ls
java-1.8.0-openjdk-amd64  java-8-openjdk-amd64
ubuntu@ip-172-31-16-80:/usr/lib/jvm$ cd java-8-openjdk-amd64/
ubuntu@ip-172-31-16-80:/usr/lib/jvm/java-8-openjdk-amd64$ ls
ASSEMBLY_EXCEPTION  THIRD_PARTY_README  bin  docs  include  jre  lib  man  src.zip
ubuntu@ip-172-31-16-80:/usr/lib/jvm/java-8-openjdk-amd64$ pwd
/usr/lib/jvm/java-8-openjdk-amd64
ubuntu@ip-172-31-16-80:/usr/lib/jvm/java-8-openjdk-amd64$
ubuntu@ip-172-31-16-80:/usr/lib/jvm/java-8-openjdk-amd64$ export JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64"
ubuntu@ip-172-31-16-80:/usr/lib/jvm/java-8-openjdk-amd64$ echo $JAVA_HOME
/usr/lib/jvm/java-8-openjdk-amd64
ubuntu@ip-172-31-16-80:/usr/lib/jvm/java-8-openjdk-amd64$ mvn -version
Apache Maven 3.6.0
Maven home: /usr/share/maven
Java version: 1.8.0_252, vendor: Private Build, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
Default locale: en, platform encoding: UTF-8
OS name: "linux", version: "4.15.0-1065-aws", arch: "amd64", family: "unix"
ubuntu@ip-172-31-16-80:/usr/lib/jvm/java-8-openjdk-amd64$ mvn validate
[INFO] Scanning for projects...
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.225 s
[INFO] Finished at: 2020-06-19T19:06:40Z
[INFO] ------------------------------------------------------------------------
[ERROR] The goal you specified requires a project to execute but there is no POM in this directory (/usr/lib/jvm/java-8-openjdk-amd64). Please verify you invoked Maven from the correct directory. -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MissingProjectException
ubuntu@ip-172-31-16-80:/usr/lib/jvm/java-8-openjdk-amd64$ cd..
cd..: command not found
ubuntu@ip-172-31-16-80:/usr/lib/jvm/java-8-openjdk-amd64$ cd
ubuntu@ip-172-31-16-80:~$ cd .ssh
ubuntu@ip-172-31-16-80:~/.ssh$ ls
authorized_keys
ubuntu@ip-172-31-16-80:~/.ssh$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/home/ubuntu/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/ubuntu/.ssh/id_rsa.
Your public key has been saved in /home/ubuntu/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:YlpjY8CMNgD5rWaZYgyKHTUOspNCaXKxp879axmlolw ubuntu@ip-172-31-16-80
The key's randomart image is:
+---[RSA 2048]----+
|+.o.             |
|+=o=o            |
|+*===.           |
|*.o+o.  .        |
|*o.=  OoS        |
|+=B.E*o+         |
|.=ooo. o         |
|  o  .o          |
|     .o.         |
+----[SHA256]-----+
ubuntu@ip-172-31-16-80:~/.ssh$ ls
authorized_keys  id_rsa  id_rsa.pub
ubuntu@ip-172-31-16-80:~/.ssh$ cat id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDWCRzNRZw7Rjae72CUTButI1nqwF7WSFNTXxAszBbfmm7K+4UqyryhFit8PHFYYQtFGzR/2SEIEnStjgawbAntn4qd3Rtvln0uamCy26FWsChUKSGHcm26ycaXxTZUtBl9qeDXPFLkz7JIyWn3mfGvI2rJBlaoB3DT3bTcH7PHO3XxFuR0WGPmVPpp6dh89bS325dGmCTicy4n+X0ulQ1gY/LXr/FDxanEmiOu7F3B+nVM5zgZ3cOUxt1uMv4QSb2ZIg+ipkYrusC1/B3WFMERbda/qW7WJkDJBC7TcUJj038T4C7xIF9/QuQExMiMCLEXme5ucTFaLrOt+5VX0QGt ubuntu@ip-172-31-16-80
ubuntu@ip-172-31-16-80:~/.ssh$ vi authorized_keys
ubuntu@ip-172-31-16-80:~/.ssh$ chmod 755 id_rsa*
ubuntu@ip-172-31-16-80:~/.ssh$ chmod 400 authorized_keys
ubuntu@ip-172-31-16-80:~/.ssh$ cat id_rsa
-----BEGIN RSA PRIVATE KEY-----
MIIEpQIBAAKCAQEA1gkczUWcO0Y2nu9glEwbrSNZ6sBe1khTU18QLMwW35puyvuF
Ksq8oRYrfDxxWGELRRs0f9khCBJ0rY4GsGwJ7Z+Knd0bb5Z9LmpgstuhVrAoVCkh
h3JtusnGl8U2VLQZfang1zxS5M+ySMlp95nxryNqyQZWqAdw09203B+zxzt18Rbk
dFhj5lT6aenYfPW0t9uXRpgk4nMuJ/l9LpUNYGPy16/xQ8WpxJojruxdwfp1TOc4
Gd3DlMbdbjL+EEm9mSIPoqZGK7rAtfwd1hTBEW3Wv6lu1iZAyQQu03FCY9N/E+Au
8SBff0LkBMTIjAixF5nubnExWi6zrfuVV9EBrQIDAQABAoIBAQCXP8lCpbZJjMx8
c9xj74R/TUP1SAu8kU+Q0tSzU2W2jYNNnX/1RV8W1nvUR0IxmiJEq3zl+6ID+kbJ
flvrv+0kJmHmPKFusYG0kyfSPLI+eC2Hi6lN9ebk4EGebpZ+NObujmV8s/xABSWP
mgVwGzFW+kgz1m7WPqvUjA+KnjyExIw7HAU/gwYi3DHq5ZTGWG/31zNzSBCfU5FL
FALWR/OduATWfPSxsXVCLdaFOkSDsRCBXtLfe0/G1sd7XyOcPVaingsJSKiMKQrr
x3/oT0OJhpQDkr021fvIAo1QMxqEc7qADjSm+/n7dXZkek1bp68SqpIsVre/AfiI
iasI1N5hAoGBAPzYDREu/R4PKd+kh223n53uFXBpOZV2qDPbAASRa9U+pHylmnHi
rj0kaB3odgaTYUcWxWaNPsaUB40teXwVGs4KbjGp0DKU7SvWamfaq+fjKw84rfps
X0EbsLhSo7GgvrS+OCxzhKcevidhJqBDRufjd2hol0zwShCNytKVGDd7AoGBANi1
DS8k8MFobJIWIt9GCYGVEPT4BARCKDGhMA1oWELCCCXw+sUf3+M1YfSDBQjgYiU4
kWkx+fTmAEjbHE4LzjTxEfvp9RDdap5EEmuOzi73dVapTiUotZroGyOdxBZFJbBb
ANNG/aqJ6cYA4LN2JRfRKEoyYKhffdL1ubIp5E73AoGAN4VdwTM3Q72CrWhckLws
oaphLND+YxKuNszVQSuJqUbbKb/XnUBwkF6JOmAMYr9EMi8O48kKSuLAkcC1l4iu
3SWvMtqeLC1Fs0WfEfUToJTipLIGiiH3/L0O3jrPVTb+CYRno2MucuAuU0ljCPgc
/tiVJOkqqCtvqBjqu7kfmzcCgYEA16R6hSJOTTebaleKxgFMrlzmrc4rOQ2YL6LF
TWI7CdtI/nBpKkWIpfDWE9lY5jdaks1SrYpkwBUrzVP0O5m1zariCXsLOYgLc4gr
iEpn1Aa9BcqeD44OASLc9rkkikCuu2ojTRrEi7KHJVh0QUDcsnGYlRTCaGn1rDqH
Wcoj/YsCgYEAhg9U6P/WM5Mf3Sr278oLaugF97G5TNogIj5pD0pM5Lt7Q8pcugi6
U6MHbZcLubC1XDcQk07KUhiqhAbcSmslVNC0AI3W2wNXiWuSUpM8/NBz5FJ9KKWI
p1hHQJ7Hn6DHToVGyPmVo4a63/8IQYZtMYqXVqCK9MKDcKa9SB1RNcM=
-----END RSA PRIVATE KEY-----
ubuntu@ip-172-31-16-80:~/.ssh$ ^C
ubuntu@ip-172-31-16-80:~/.ssh$ which java
/usr/bin/java
ubuntu@ip-172-31-16-80:~/.ssh$ ^C

----------------------------------------
1	BIOS Changes

Note:  Current models are shown in bold.
1.1	Lenovo
1.1.1	T470/T460/T450/T440

•	Security > Security Chip > Security Chip: Enabled
•	Security > Virtualization > Intel (R) Virtualization Technology: Enabled
•	Security > Virtualization > Intel (R) VT-d Feature: Enabled
•	Security > Secure Boot
o	Windows 7: Secure Boot: Disabled
o	Windows 10:  Secure Boot: Enabled
•	Startup > UEFI/Legacy Boot:  UEFI Only (GPT Boot Media)

1.1.2	X1 Carbon 5th Gen
•	Security > Virtualization > Intel (R) Virtualization Technology: Enabled
•	Security > Virtualization > Intel (R) VT-d Feature: Enabled
•	Security > Secure Boot
o	Windows 7: Secure Boot: Disabled
o	Windows 10:  Secure Boot: Enabled
•	Startup > UEFI/Legacy Boot:  UEFI Only (GPT Boot Media)

1.1.3	M900
•	Security > Security Chip > Security Chip: Active
•	Security > Virtualization > Intel (R) Virtualization Technology: Enabled
•	Security > Virtualization > Intel (R) VT-d Feature: Enabled
•	Security > Secure Boot
o	Windows 7: Secure Boot: Disabled
o	Windows 10:  Secure Boot: Enabled
•	Startup > UEFI/Legacy Boot:  UEFI Only (GPT Boot Media)

1.1.4	M93p (Legacy)

•	Advanced > CPU Setup > Intel (R) Virtualization Technology: Enabled
•	Advanced > CPU Setup > Intel (R) VT-d Feature: Enabled
•	Startup > CSM: Yes
•	Startup > Boot Mode: UEFI Only (GPT Boot Media)

1.1.5	M92p/M91p (Legacy)

•	Advanced > CPU Setup > Intel (R) Virtualization Technology: Enabled
•	Advanced > CPU Setup > Intel (R) VT-d Feature: Enabled
•	Devices > ATA Drive Setup > Configure SATA as:  AHCI
•	Startup > CSM: Yes
•	Startup > Boot Mode: UEFI Only (GPT Boot Media)
•	Security > Secure Boot
o	Windows 7: Secure Boot: Disabled
o	Windows 10:  Secure Boot: Enabled

1.1.6	T430/T420 (Legacy)

•	Security > Security Chip > Security Chip: Active
•	Security > Virtualization > Intel (R) Virtualization Technology: Enabled
•	Security > Virtualization > Intel (R) VT-d Feature: Enabled
•	Security > Secure Boot > Secure Boot: Disabled
•	Startup > UEFI/Legacy Boot:  Legacy Only
•	Config > Serial ATA (SATA) > SATA Controller Mode Option:  AHCI

1.1.7	X1 Carbon 4th Gen/3rd Gen/2nd Gen (Legacy)
•	Security > Security Chip > Security Chip: Active
•	Security > Virtualization > Intel (R) Virtualization Technology: Enabled
•	Security > Virtualization > Intel (R) VT-d Feature: Enabled
•	Security > Secure Boot
o	Windows 7: Secure Boot: Disabled
o	Windows 10:  Secure Boot: Enabled
•	Startup > UEFI/Legacy Boot:  UEFI Only (GPT Boot Media)


1.2	Dell
1.2.1	Latitude E7270

Note:  This model should use GPT/UEFI boot media and boot options.

•	Settings > System Configuration > SATA Operation > AHCI
•	Settings > Security > TPM 1.2 Security > TPM On (Place a check in the checkbox, then more settings will display)
•	Settings > Security > TPM Security > Activate (Radio button)


1.2.2	Latitude 7370

Note:  This model should use GPT/UEFI boot media and boot options.

•	Settings > General > Advanced Boot Options > Uncheck “Enable Legacy Option ROMs”
•	Settings > System Configuration > SATA Operation > AHCI
•	Settings > Security > TPM 1.2 Security > TPM On (Place a check in the checkbox, then more settings will display)
•	Settings > Security > TPM Security > Activate (Radio button)


1.2.3	Latitude E5450/E7250/E7450 (Legacy)

•	Settings > Security > TPM Security > TPM Security (Place a check in the checkbox, then more settings will display)
•	Settings > Security > TPM Security > Activate (Radio button)
2	Other Hardware
2.1	Microsoft Surface Pro 4
•	Use a USB hub to connect a USB Ethernet adapter and your USB boot media.
•	Use UEFI/GPT boot media and install Windows 10.
3	Document History

Author	Document Status	Document Version	Date Modified	Sections Changed / Description
Jared Ezyske	Draft	0.1	4/24/15	Document created
Jared Ezyske	Production	0.2	4/28/15	Added models
Jared Ezyske	Production	0.3	June 2016	Various models added
Jared Ezyske	Production	0.4	8/31/16	UEFI, model tweaks
Jared Ezyske	Production	0.5	9/16/16	Added models
Jared Ezyske	Production	0.6	10/18/16	Models, tweaks
Jared Ezyske	Production	0.7	11/10/16	Creating boot media, tweaks
Jared Ezyske	Production	0.8 - 	2017	Added 2017 models
				
				
				
				


7Unable to open excel files (file is corrupt)
Change the 'Trust Center' Settings: Sometimes, the enabled protected view settings under 'Trust Center' prevent the Word file from opening. Mentioned below are the steps to change the settings of 'Trust Center':
•	Open your MS Word application.
•	Click 'File >> Options'.
•	Select the 'Trust Center' and press button under 'Trust Center Settings'.
•	Click 'Protected View'.
•	Uncheck all the options available under 'Protected View' and click 'OK' to confirm.
•	Restart MS Word and now, try to open your corrupt Word document.
 Manual Setting of 'Component Security':  To change these settings to default settings, follow the below-mentioned steps:
•	Go to 'Start' and in the search box, type 'dcomcnfg'. After that, select 'dcomcnfg' from the program list.
•	Go to the navigation pane and expand the 'Component Services'. Then, go to 'Computers' and expand it. After that, right-click on 'My Computer', and then click 'Properties'.
•	Open the 'Default Properties' tab and set Default Authentication Level: Connect, Default Impersonation Level: Identify and click 'OK'.
Right click on the corrupted file and you see a option something like unblock content
How to set Set java path
Here are the typical steps to set JAVA_HOME on Windows 10.
1.	Search for Advanced System Settings in your windows Search box. Click on Advanced System Settings.
2.	Click on Environment variables button: Environment Variables popup will open.
3.	Goto system variables session, and click on New button to create new variable (HOME_PATH), then New System Variables popup will open.
4.	Give Variable Name: JAVA_HOME, and Variable value : Your Java SDK home path. Ex: C:\Profram files\java\jdk1.8.0_151 Note: It should not include \bin. Then click on OK button.
5.	Now you are able to see your JAVA_HOME in system variables list.
6.	Select Path (from system variables list) and click on Edit button, A new pop will opens (Edit Environment Variables). It was introduced in windows 10.
7.	Click on New button and give %JAVA_HOME%\bin at highlighted field and click Ok button.

Unable to update bit locker password

      run Manage-Bde -protectors -Delete C:
     Reboot the machine.
     Run Manage-bde -protectors -Add C: -TPMAndPIN.
    Checking within the BIOS
      Once inside the BIOS we need to confirm something :
1.	Go to Security > TPM Security.
2.	Ensure the checkbox for Activate is selected.
3.	Save and Exit from the BIOS.


Firefox backup path
%APPDATA%\Mozilla\Firefox\Profiles\

That's neat. But where it really becomes helpful is when you begin to pass arguments in the URL to tell Software Center where to go. So, let's cut to the chase and give you the good stuff. Here are the four links I need in order to generate the shortcuts shown above:
•	Install Software: softwarecenter:Page=AvailableSoftware
•	PC Updates: softwarecenter:Page=Updates
•	Upgrade Windows: softwarecenter:Page=OSD
•	Check Device Compliance: softwarecenter:Page=Compliance
Excel 2013: Not enough system resources to display completely
•	If you have any COM add-ins installed, un-install them unless they are absolutely required or just untick them to test. ...
•	To see if you have multiple sessions open, press CTL-ALT-DELETE and check how any Excel applications are running. ...
•	Excel may think your worksheets are larger than you do.


Please use below commands to add/remove members from DL.


1.	Click on Run %SYSTEMROOT%\System32\rundll32.exe dsquery,OpenQueryWindow



Win + Shift + S will capture a screen region from any application and copy it to clipboard — powered by Snipping Tool's new "/CLIP" command-line. This means that you can no longer use this keyboard shortcut to insert a screen clipping into yourOneNote pages. However, there is a workaround.



https://pcsupport.lenovo.com/in/en/warrantylookup lenovo warranty status

Get-AppxPackage -allusers | foreach {Add-AppxPackage -register "$($_.InstallLocation)\appxmanifest.xml" -DisableDevelopmentMode}
Windows defauls apps to orginal
outlook /cleanrules 

Lock screen enable 
Computer\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\System
Auth code: 66072 
Bitlocker key required to login
1.           RUN  Gpupdate /force 
2.           Open Elevated CMD 
3.           manage-bde -on c: -tp -rp
Set pin (Ex: welcome1)
Make sure make sure to copy the “Numerical Password, TPM and PIN” in a secure location away from that computer where this command is executed. This saved recoverykey password will help to unlock the encrypted volume in case of any issues.
4.           Restart the machine.
5.           Machine start prompts for bit locker.
6.           Enter the key set by associate earlier (Ex: welcome1) .
7.           Check the encryption status by running this command Manage-bde -status C:
For logging off users remotely, use below commands. Make sure the user name before you logoff.

1.	quser /server:Hostname

 
2.	Logoff sessionID /server: Hostname

 
outlook.exe /resetnavpane

Enable the cdrom process

Regedit\Hkey Local machine\Controlset001\Services\CDROM ( Change value in start 4-1)

Computer\HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\USBSTOR(Change value in start 4-
Speedtest.net

Wifi displays
netsh wlan show drivers
Wlan AutoConfig—automatic in services.msc



























