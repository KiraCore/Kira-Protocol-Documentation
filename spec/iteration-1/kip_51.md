# [⏎](README.md#Roadmap) KIP_51
> Deployment and Management Scripts

We have to create deployment and management scripts that will enable ease of operating validator, full nodes and sentry nodes by using a single console tool called `kira`. To ensure consistency we will only support a single operating system - [Ubuntu 20.04 LTS](https://releases.ubuntu.com/20.04/) and all scripts will be written using [bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)).

This KIP must be tested using [VMWare Workstation 15.5+](https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html). After installation of Ubuntu, developer/tester should zip and backup all the VM files for the ease of instant recovery.

## Abstract

1. User installs Ubuntu 20.04
2. User opens terminal and logs in as sudo
3. User executes a command that will setup the environment by downloading setup file from github or other source, check integrity of the file, start it and install all essential dependencies
4. Setup scrip will further download and install `kira` management tool
5. By typing `kira` in the terminal user will have ability to deploy, scale and manage his infrastructure

## Setup

It must be assumed that a fresh Ubuntu release will not contain many essential tools such as curl or git. We have to create a script that will install all essential dependencies along `kira` management tool. The setup script must be possibly short and only reference and download all other dependencies and deployment script.

Integrity of the script must be verifiable by the user before it's execution (SHA256 check). All the necessary setup commands must be compressed into a single line of code that can be easily copied and pasted into the terminal.

### Example Setup Command

```
sudo -s

cd /home/$SUDO_USER && \
 rm -f ./setup.sh && \
 wget <URL_TO_THE_SCRIPT> -O ./setup.sh && \
 chmod 555 ./setup.sh && \
 echo "<SHA_256_CHECKSUM> setup.sh" | sha256sum --check && \
 ./setup.sh
```

## Installation

All components of the infrastructure will be deployed within the docker containers, for that reason we have to pre-install latest version of docker and create docker network interface. 






