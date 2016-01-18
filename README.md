# WindowsDocker

Follow installation of Docker Machine from official website - 

Ensure docker image is created in Virtual Box, but not running.

$ cd "C:\Program Files\Oracle\VirtualBox"
$ VBoxManage sharedfolder add boot2docker-vm --name mydata --hostpath "D:\development"

Start docker image

ssh into docker machine
user: docker
pass: tcuser

$ sudo mkdir -p /data
$ sudo mount -t vboxsf -o "defaults,uid=33,gid=33,rw" mydata /data

Back in host environment

$ docker run --volume /data:/data --name mydata dylanlindgren/docker-laravel-data

Build images

## Issues
Went to the C:\Program Files\Oracle\VirtualBox\drivers\vboxdrv directory, right clicked on VBoxDrv.inf and selected Install. I then went back to my console and typed 'sc start vboxdrv' and got this:

SERVICE_NAME: vboxdrv
TYPE : 1 KERNEL_DRIVER
STATE : 4 RUNNING
(STOPPABLE, NOT_PAUSABLE, IGNORES_SHUTDOWN)
WIN32_EXIT_CODE : 0 (0x0)
SERVICE_EXIT_CODE : 0 (0x0)
CHECKPOINT : 0x0
WAIT_HINT : 0x0
PID : 0
FLAGS :

Went back to VirtualBox and was able to start the Ubuntu virtual machine.
