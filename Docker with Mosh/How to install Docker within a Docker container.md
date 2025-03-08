$ docker ps  
  
$ docker exec -u root -it <ID/NAME> bash  
  
check distro:  
$  cat /etc/os-release  
should be a Debian flavor  
  
easiest way I find for docker engine install:  
$ curl -fsSL [https://get.docker.com](https://get.docker.com) -o get-docker.sh  
  
$ sudo sh get-docker.sh  
  
------  
  
check if docker daemon (docker engine) is running according to systemd:  
$ systemctl docker status  
  
if no:  
$ sudo systemctl start docker  
$ sudo systemctl enable docker  
  
then check again:  
$ sudo systemctl status docker



Extra
$ docker ps  
$ docker rm -f <ID/NAME>  
  
$ sudo docker run --privileged --name jenkins -d -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts