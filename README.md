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
   
   ## 2.2 Getting Help
   ### 2.2.1 Man page
   Traditional package documentation for application usage
   ```man <cmd>```
   When you run a command, you can check the exit status by running
   `echo $?` after that command
   if return 0, means ok.
   After you open the man page, you can search by type "/" following the things you want to search
   ```man -k [commands you want to search for manual]```
   or
   ```apropos [commands you want to serach for manual]```
   ### 2.2.2 Info pages
   It normally provide more detailed information about a command than its man page.Additionally, info uses a structure for    linking pages together, and may be assembled into a larger collection.
   ```info <command>```
   ```htop #display running processes in a pretty format```
   ### lab
   determine how many lines the file contains
   
   ## 2.3 Using Files and directories
   ### 2.3.1 Files and directories
   #### FHS
   Filesystem and Hierachy standard defines the structure of the file system on linux
   The Root FileSystem
  - /           the root directory, the top of the file system
  -/bin         user binaries, it contains the commands the user can run
  -/boot        contains the files to boot the linux system
  -/dev         device files
  -/etc         configuration files, the installed applcation config files will be here
  -/home        user home directire
  -/lib         shared libs
  -/mnt         shared libariries
  -/opt         optional packages
  -/proc        kernal and process files
  -/root        root user home directory
  -/run         application state files
  -/sbin        system admin binaries
  -/srv         service data
  -/tmp
  -/usr
  -/var
  #### working around
  Go up to last location ```cd -```
  Go up two levels ```cd ../..```
  
  ### 2.3.2 Hidden Files
  hidden files maybe listed via ls using the -a option, to show all files
  ```ls -a  #show all files include hiddent files```
   
  ### 2.3.3 Home directories
  A home directory in created undre /home, for each ordinary user
  Checks all of the user under this linux system ```cat /etc/passwd```
  e.g.output consists of 
  username, userid, usergroupid,and the bash file it received.
  Check variables ```env```
  
  ### 2.3.4 Absolute and relative Paths
  #### absolute path
  starting with a /
  ```pwd``` shows absolute path
  #### relative path
  
  ###Lab
  - Determine which file is the oldest ```ls -lAt ~/Practice/Test/var/log/```To list the directory and sort by date, we use -l for "long listing", -A for "almost all", and -t for "sort by time".
  
  ### 2.4 Creating, Moving and Deleting Files and directories
  #### 2.4.1 Files and directories
  
  #### 2.4.2 Case sensitivity
  ```mkdir new folder #this will create two directory so```
  replace by ```mkdir new\ folder```
  - Determine Which File Is the Largest ```ls -lS ~/Practice/Test/var/log/ ```
  To list the directory and sort by file size, we use -l ("long listing") and -S ("sort by file size").
  - Determine when the file was last accessed ```ls -lu ~/Practice/Test/sos_commands/networking/netstat_-W_-neopa #u access time ```
  
 #### 2.4.3 Simple Globbing
 Globbing is using partial matching to work with groups of files and directories.
 It is primarily used to match patterns in filenames or text by using a wildcard character to create the pattern.
 - ? matching any single character
 - * matching any number of characters
 - [] match a character from a range
 ```ls ????[1-4] #match something start with any four characters but ends with a range between 1 and 4```
 ```ls *[[:digit:]] #give anything ends in any digits``` this is same as ```ls *[0-9]``` 
 ```ls *[[:upper:]] give anything ends with uppercase``` this is same as ```ls *[A-Z]```
 ```ls *[[:lower:]] give anything ends with lowercase``` this is same as ```ls *[a-z]```
 ```ls *[[:alpha:]] give anything ends with lowercase``` this is same as ```ls *[a-zA-Z]```
 ```ls *[[:alphanum:]] give anything ends with lowercase``` this is same as ```ls *[a-zA-Z0-9]```


### Lab
```cp -R Practice/Test Report #we need -R cause we are coping a file under a folder```
## 3 The power of command line
### 3.1.1 Archiving files on the command line
  
  
