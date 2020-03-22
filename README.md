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
 
 ## 1.4 working in Linu
 ### 1.4.1 Desktop skills
 Popular Desktop Environments
 - LXDE
 - MATE
 - XFCE
 - Cinnamon
 - Gnome
 - Unity
 - KDE
 
 Userspace and Privacy
 A user has a home directry under /home/
 ```ls /home/ #check how many users, each user wouldn't have permission to test other users's file, ReadOnly permission```
 There is a Root user, if you have root access, you have access to everything
 
  ### 1.4.2 CLI
  Show hostname ```hostname```
  SSH remote system ```username@hostname``` or ```username@remote_id```
  
  Localclient[SSH client]-------------> Server (connecting over the network port 22)
  
  ### 1.4.3 Industry Uses
  #### Virtualization
  ##### Physical host computer
  It will have physical RAM Storage and CPU.With V, we have virtual guest, virtual box could be used to created virtual machine, vm is assigned some amount of memory and storage. 
  
  ##### Cloud Linux
  
  #### Lab
   View the release files by using globbing to pick up everyfile that contains the word "release" in the /etc/ directory
   ```cat /etc/*release*```
   View the issues files
   ```cat /etc/*issue*```
   Run a utility to determine the linux distribution
   ```lsb_release -a```
   ```hostnamectl```
   
   ## 2.1. Finding your way in linux
   ### 2.1.1 Basic shell
   STDIN is input, will be executed as a process
   STDOUT is output
   Output ->   STDOUT ->Display
         \           \
          \> STDERR -> \> Redirection or Pipeline
   
   ### 2.1.2 Command linx syntax
   ```ls -l # long listing```
   ```ls -ls #size information```
   ``` ls -alsh # for all,long listing,size, human readable```
   ``` man ls #check doc for the command```
   
   ### 2.1.3 Variables
   Using var to store values for reference
   - Assign a variable , use a $ to reference the variable
   ```test_variable="This is a variable"```
   ```echo $test_variable```
   - Bash variables
   $HOME the current users's home diretory
   $PS1 the primary prompty string
   ```[\u@\h \W]\$```
   ```[username@hostname workingdirectory]```
   $PATH a colon-separated list of directories where the shells looks for commands
   
   var1 will be assigned what ever exected in the ()
   ``` var1=$(ls)```
   
   ### 2.1.4 Quoting
   Preserve input that contains special characters or spaces
   #### Escape Character
   backslash \ is the escape character to preserves the literal value of the next following character, with the exception of 
   newline.
   ```var1= Some\ value```
   ```echo $var1```
   ```Some value```
   #### Single quotes
   preserve every literal value, including escape character
   #### Double quotes
   preserve most literal values, except $,single quote and \
   
   ### Lab
   check current working directory ```pwd```
   determine which users are currently log in ```w```
   dterminw which users last logged in to the system, as well as the last time the system was booted by running
   ```last```
   record your findings in `/home/cloud_user` by writing the output of the previous commands into a new file
   ```w > log.txt #replace the original file``` 
   ```last >> log.txt #append to the original file```
   
   list the current environment variables, and locate the $PATH variable
   ```env```
   examine the $PATH variable
   ```echo $PATH```
   append scripts directory to $PATH
   ```PATH=$PATH:$HOME/scripts```
   if we log out, we will lose our ability to run the script without specifing the path, so we need to make our change
   permanent, we can do this by modifying the ~/.profile
   ```echo 'PATH="$PATH:$HOME/scripts"'>> ~/.profile```
