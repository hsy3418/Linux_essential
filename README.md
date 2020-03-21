# Linux_essential


## 1.1. Linux Evolution and popular operating system
### 1.1.1 Linux distribution
Linux distribution: e.g. ubuntu
```
lsb release -a # check the distribution version
```
#### kernel
It is a framework that connects the application layer to the hardware of a computer. Within the low-level abstraction process, system calls are made to the kernel. Hardware is incorporated into the file hierachy through ```/dev``` and ```/sys``` directories, and process informations is mapped in ```/proc```
```uname -r #check the version of the kernel``` 

#### GNU Core Utilities
They are basic file, shell, anad text manipulation utilieties of the GNU OS. Examples: Set and change file permission and ownership, concatenate and write files, exit status, listing directories and files. ```ls```

#### X Server
Enable us to make use of GUI.

#### Graphic interface

### Popular Linux Distributions
- Red Hat Enterprise Linux
- CentOS
- Ubuntu
- Fedora
- Debian
- openSUSE

### 1.1.2 Linux embeded system
A combination of hardware and software for a purpose

- Android
- Rpi
Hardware
Low-level interfaces
Networking-Filesystem
High-level abstractions
Libraries-applications

### 1.1.2 Linux in the cloud
Cloud: software and services that run and are available on the internet

### Lab
- connect to the remote server using ssh client(address, username, password
```SSH Username@hostIP```
- Run below commands
Show username```whoami``` 
Show current directory ```pwd```
Show listing of last logged in users```last```
Show how long the system has been running ```uptime```
Show manul of the command  ```man whoami```

## 1.2 Major open source applications
### 1.2.1 Desktop applications
- OpenOffice
- LibreOffice
- Web browsers
### 1.2.2 Server applications
#### Web Server applications
- Appache HTTP Server, it listens on the port which is listening on incoming traffic, typicall on port 80 or 443
- Nginx: can be used for reverse proxy, load balancing, mail proxy and HTTP caching
#### DB Server
- MySQL
- MariaDB
#### File sharing applications
- Samba: don't share file over internet
- NFS: distributes file system protocal, permitting clent hosts to access files and directories over the network as local storage
e.g
```df -h | grep /dev/sda1```
it shows your storage, but you could partition it and create a NFS export, other computers on the network could attach to this NFS export and use it as if it's their own network. ShareFiles
 #### Cloud 
 - owncloud
 - nextcloud
 ### 1.2.3 Development languages
 #### Shell
 Shell script is designed to be run by the command line interpretor using scripts languages. Shell scripts are often used to automate strings of commands with some manner of logic applies. Bash is the most common shell.
 ```for i in {1...100}; do touch newfile_$i;done```
 ```rm -f newfile*```

 ### 1.2.4 Package Management Tools
 
 #### Package
 It is a collection of the files needed to install an application. So prior to packages, applications are installed via the source code, source code was placed on the local file system, then the binaries are compiled on the host. 
 
 ##### dpkg:Debian Package
 - apt-get: Advance package tool, they also
 
 
 ##### rpm： Red hat package manaer
 - Yum: yellowdog updater, Modified
 
 ### Lab
 #### Install a RPM package
 - Install a `htop` RPM package
 ```sudo rpm -i [package.rpm]```
 - Run the `htop` Application
 ```htop```
 - Remove `htop` package
 ```sudo rpm -e htop```
 #### Install a DEB package
 - Install a `htop` RPM package
 ```sudo dpkg [package.deb]```
 - Run the `htop` Application
 ```htop```
 - Remove `htop` package
 ```sudo dpkg -e htop```
 #### Compiling from source
 a source code archieve is in the file
 - Locate and extract the source file achieve
 ```tar xzf [file.tar.gz] #extract the archieve into the new folder```
 - Change to the htop director
 ```cd htop-2.2.0```
 - Run the configuration script to prepare the source
 ```./configure```
 - Compile the souce code to usable binaries
 ```make```
 - Install the binaries
 ``` sudo make install```
 - Run htop
 ``` htop```
 - Remove installation
 ```` sudo make uninstall```
