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


