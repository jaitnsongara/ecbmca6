Date 22.2.21

GIT e-Notes

Step-1  How to install git 

   Install git 
Yum install git -y
Step-1.1  Create ssh key (ED25519  / RSA)

	ssh-keygen   -t   ed25519   -C   “Your Email”

Step-1.2  How to check your Public key in Linux OS and then share this public key with your instructor via email / whatsapp / sms / or any other medium
	
cat /root/.ssh/id_ed25519.pub

Step-1.2  When your instructor added your key then test ssh as following:
			
		ssh    -T   git@github.com

Step-2   git init 
Step-3    git config --global user.name "YOUR-GIT-NAME"

Step-4  
git config  --global  user.email “YOUR-EMAIL-ID”

Step-5    Initialize the Git commands in your PC
 git init 

Step-6   go  to   /opt/     and create directory github.com

cd   /opt/
   			mkdir  github.com
cd   github.com
Step-7    git clone  git@github.com:cdtsbikaner/ecbmca6.git

Step-8     show all files at current working directory 

			ls  -l
Step 8.1    Now enter the Clone directory recently fetched from remote

cd   ecbmca6

Step-9    Show currently existing  branches 
	
 			git branch

Step-10  Create a new branch 

        git branch  BRANCH-NAME 


Step-10.1 create new branch & checkout into new branch
git  branch  dev

git  checkout  dev

Step-10.2  create a new branch by cloning current  & switch to new branch 

     		  git   checkout  -b  feature1

Step-11      Check status of current branche

  git   status

Step-12    Add those untracked files which are available in the current folder (Locally)
 
git  add  -A
OR 
git  add .

Step-13   You can not upload into Github remote directory until and unless you dont commit your work:

git  commit  -m  “Any message you can write”

Step-14  Cross check your branch 

 git status 

Step-15  Now push newly created local branch from LOCAL - ---->  to   Remote Server 

 git push  origin  dev

Step-16 Cross check at github on Browser 
Whether data is available there or  not ?

Step-17  If you want to see all branches available on remote then;
17.1 :    switch to branch master

		git checkout master

17.2 :    make a pull / fetch request

		git fetch 

Step-17  How to delete branch at local and Remote side

// delete branch locally
git branch -d maninder

// delete branch remotely
git push origin --delete maninder

--------------------------------------------------------------------





Solved assignment:  
1. Go to   dev branch 
	git branch 

	git   fetch   /  pull
	 git checkout dev	
	 git    pull   origin   dev

ls  -l 

	 
2.  Create a new branch and checkout into a new branch  (For example  dev  ->   NewBranchName )

            git checkout  -b  your-nick-name        

 3.     Check your branch name  
			git branch 

			
4. Edit existing file (contact.php)  the Add file in staging area
	echo “BBYE WORLD”    >>   contact.php

 4.1 add newly updated file i staging area
		git     status 
git     add   .
		
5. Commit file
		git commit -m   “Added new data”
6. Push file 
6.1   To push your branch name 

  git  push   origin TYPE-YOUR-BRANCH-NAME

6.2   Push your data on your Remote branch 

       git    push   

7. Tell the instructor to check  OR Check github yourself.



---------------------xxxxxxxxxxxx--------------











------------------------------------------------------------------
Date 17.2.2021
switch  …. Case
array
dialogue box
-----------------------------------------------------------

	a[0]  =  "Virat kohli"
	a[1]  =  "Kapil dev"
	a[2] =    12345
	a[3] =  556.77
	a[4] = true

	INDEX/Key	VALUE

	echo  ${a[0]}
	echo  ${a[1]}
------------------------------------------------------------
	
	userdata=( "Maninder SIngh" 9898989898 1000.50 )
	echo ${userdata[2]} 
-----------------------------------------------------------------------------


Telent -Server 

To communicate between two devices medium are know as TELNET. 
Its an insecure communication channel.

TCP  --> 23

RHEL6  / CENTOS6  --->   OLD way which contains more configuration for telnet access. 

To configrure telnet we use moslty Firewall rules.

yum install telnet telnet-server*  -y 


Telnet has no deamons / Service in CEntos 7 / RHEL7, Actually i use Socket file.
Socket file is use as IPC ( Inter process Call) 

systemctl  status  telnet.socket


systemctl start  telnet.socket

systemctl enable telnet.socket

netstat   -plant 


--------------------------------------------------------------------
Go to windows control panel 

Open Add remove program section 

Click on Turn windows features on / off
    -  Add telnet client service 
	PRESS OK

Open Command prompt at Windows machine and use telnet with ip

	telnet  IP-Address-Of-Server
NOTE--> It Wont allow to acces server 

Go to Linux machine again and do the following needful:-
--------------------------------------------------------------

Step-1   open securetty file 
	 vim /etc/securetty

Step-2  Go to bottom of file and enter

	pts/0
	pts/1
	pts/2
	pts/3
	pts/4
	pts/5
Step-3 Go to Window Command propt again and try to login 

		telnet  Server-IP


--------------------------------------------------------------------

Actual use of telnet is to check if the port number of service is active or not.

	telnet   IP   portNumber



----------------------------------------------------------
Script-1 (17.2.21)
switchcase.sh 

#!/bin/bash
echo "Enter morning / evening / night for auto response"
while :
do
read inputstr
        case $inputstr in
        morning)
                echo "Good morning"
                ;;
        evening)
                echo "Good evening"
                ;;
        night)
                echo "Good night"
                ;;
        *)
                echo "Sorry i did not understand"
                ;;
        esac
#echo "TO EXIT FROM THIS press ctrl + c "
exit 0
done;
----------------------------------------------------------

Script-2 (17.2.21)
artest.sh 
#!/bin/bash
#---------------First way to create array-----------------
cricket[0]="Kapil Dev"
cricket[1]="Rahul Dravid"
cricket[39]="Sachin"
echo ${cricket[0]}
echo ${cricket[39]}

#--------------Second Way to define Array in Shell----
mydata=("Maninder Singh BHui" 123456 89.45 10000 [99]=true)
echo ${mydata[0]}
echo ${mydata[3]}
echo ${mydata[6]}
echo ${mydata[2]}
echo ${mydata[99]}


#----------------third way to cerate an array------------
#    $*  -->  Print All data
#    $@  --> Print values in Array
#    $#  --> Count all the elements
echo -e "--------------ENTER FRUITS NAME--------- :"
read -a  fruits
for i in "${fruits[@]}"
do
        echo "You Entered fruits[$i] ---->  $i "
done

-----------------------------------------------------------------










Date: 16.2.21
Shell Script-1
Name :    mytask.sh
-------------------------------------------------------------------------------------------
#!/bin/bash
#echo "Hello World"
#echo "Enter 1st number "
#read a
#echo "Enter 2nd number "
#read b
#read -p "Enter 1st number " a
#read -p "Enter 2nd number " b
#expr $a + $b
#a=15                  #  integer Data type
#b=30                  #  integer Data type
#c="My friend John"    #  String Data type
#expr "$a+$b"
#expr '$a+$b'
#expr $a + $b
#sum=$(( a + b ))
#echo "Sum is $sum"
read -p "Enter 1st number a :" a
read -p "Second number b: " b
#sum=$(( a+b ))
#sum=$[ $a + $b  ]
sum=$(( a+b ))
echo "Total of a+b is  $sum"


--------------------------------------------------------------------------------------------------




Shell Script-2
Name :    calcseconds.sh

#!/bin/bash
hr_in_day=24
min_in_hr=60
sec_in_min=60
#total_sec=$(( hr_in_day * min_in_hr * sec_in_min ))
total_sec=$[ $hr_in_day * $min_in_hr * $sec_in_min  ]
echo "Total seconds in a day $total_sec"

-------------------------------------------------------------------------------------------------
Shell Script-3
Name :    variable.sh
#!/bin/bash
read -p "Enter 1st number :" x
read -p "Enter 2nd number :" y
if [ $x -ne $y ];then
        echo "$x is not quales to $y"
else
        echo "Both values equals"
fi

--------------------------------------------------------------------------------------------------

Shell Script-4
Name :    looptest.sh
#!/bin/bash
for i in {1..20..4}
do
    echo "Welcome $i times"
done

--------------------------------------------------------------------------------------------------
Run Script on Command Line (For Loop)


for i in {1..10};  do echo "hello $i"; done;
---------------------------------------------------------------------------------------------------


Assignment :

  Find all files in a Specific directory and copy them under  /mnt  (For loop)
Find all files in a specific directory  which contain word “is”  and we need to replace such word with “was”  (for loop)
No need to create shell , we need to test assignment on Command line 

-------------------------------------------------------------------------------------------------
Command Line Arguments in Shell Script

$#    Stores the number of command-line arguments that
      were passed to the shell program.
$?    Stores the exit value of the last command that was
      executed.
$0    Stores the first word of the entered command (the
      name of the shell program).
$*    Stores all the arguments that were entered on the
      command line ($1 $2 ...).
"$@"  Stores all the arguments that were entered
      on the command line, individually quoted ("$1" "$2" ...).

Ex:
As Brian commented, here is a simple example. If you run following command:
./command -yes -no /home/username


$# = 3
$* = -yes -no /home/username
$@ = array: {"-yes", "-no", "/home/username"}
$0 = ./command, $1 = -yes etc.
--------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------

Shell Script-5
Name :    setarguments.sh

#!/bin/bash
set Hello how are you well i am waiting for you all in Jaipur.
echo "$#"
echo "$@"
echo "$*"
echo $0
echo $1
echo $2

Save  & Exit from Shell  
Move this script under /usr/bin/
Create some text file and run as follow
  Setvariable.sh 

----------------------------------------------------------------------------------------------------------------



https://www.linode.com/docs/guides/introduction-to-firewalld-on-centos/


firewalld in Centos  (iptables old version)
It is  software firewall 
Firewall is a way to filter or Prevent unwanted / unauthorized packets coming from outside the network into our network.

Step-1  install auto compilation shell in centos7

 yum install bash-completion bash-completion-extras

Step-2   Compile shell
	
	source /usr/share/bash-completion/bash_completion

Step-3  test  / compile shell
		
		firewall-cmd  --list-all-zones | less
Step-4 check active zone with brief information

		firewall-cmd --list-all
-------------------------------------------------------------------------------
    tar cfpz mydata_etc.tar.gz --exclude=/etc/yum.repos.d   /etc/
 
   tar  -tf  mydata_etc.tar.gz |  less
   tar cfpz mydata_etc.tar.gz --exclude=/etc/yum*   /etc/
  tar  -tf  mydata_etc.tar.gz |  less
systemctl strart  firewalld
   systemctl start  firewalld
  systemctl enable firewalld

----------------------------------------------------------------------------------


To Check Virtualization on Base machine 

Step-1  boot with Live USB then ;

Step-2 and open terminal and use following command wheather your CPU support virtualization or  not ?

	cat  /proc/cpuinfo   |   grep lm

  	cat  /proc/cpuinfo   |   grep vme

	cat  /proc/cpuinfo   |   grep vmx

------------------------------------------------------------------------------ 

Question 

Create daily backup + compress of   /etc/  and move to /opt/  directory  at specific time  12:30 pm 

	crontab  -e 
	
Hint all backup / tar file under following default location:

	/root/ 


Date:   11.2.2021  

Backup in Linux OS

1.  tar  (*.tar)
	Data will compress in less size, only file system backup will create within tar file

2.  tar  ( *.tar.gz )   

	Backup + Shrink (Compress)
---------------------------------------------------------
How to extract Backup file 

	 Extract backup (Untar)  
   	*.tar
	*.tar.gz
------------------------------------------------------------------------------

du   -hs  *

Disk Usages   
-h  ->  human readable 
-s  -> Show 

* ->  All files and directory
------------------------------------------------------------------------------
Example:    
du  -hs  /etc/
 Now create back up only of /etc
	


tar cpf  my_etc_backup_20210211.tar  /etc/

  c -> create backup  
  p->  preserve permission bit
  f -> file   
     
 Create *.tar.gz file 
	tar  cpfz  my_zip_backup_etc_11022021.tar.gz    /etc/

To view tar file or tar.gz file content without extract :

	tar  -tf my_etc_backup_11022021.tar   |  less
  
Extract (untar) tar file (  Unzip  )
	
	tar -xf  my_etc_backup_11022021.tar  

Extract at specific location 
		
	tar  -xf my_etc_backup_11022021.tar   -C   /opt




google


1.  Set Hostname in Linux
	
	DN  -> Domain Name    ( ecb.ac.in )
	FQDN ->  Fully qualified domain name ( www.ecb.ac.in )

Note:  the host name of system is FQDN.

Set hostname   (Using Command Line)
	hostnamectl   set-hostname  www.mylab.com
Set hostname in file 

	/etc/hostname 
		Type hostname and exit then exit
	
Check run time hostname 
	bash 

2.  Cross check hostname 

	hostname
-------------------------------------------------------------


CronJob
	Deamon : -->  crond 
	service : -->  chrony
	configuration file : -->    /etc/crontab (no change require)
	Command :---->	 crontab  -e   


	 *  *   *   *  *    Command 
	M   H   

Different types of Comments in linux 
	
	#
	;

----------------------------------------------
Step-1  crontab  -e
Step-2    25 11  *  *  echo "Hello"
Step-3  Send output on terminal
		tty
Step-4  crontab -e
	31 11 * * *  echo  "Hello"  >  /dev/pts/0

Step-5  To list all crons
	crontab -l

Step-6 To use cron for specific user (Root)
	crontab -u  lyne  -e 
Step-7 Create a simple Shell script and execute via
	cronJob
  43 11 * * *  sh /root/myscript.sh







	


		



TASK TO BE DONE BY TODAY 

at   vs   cronjob
Ssh-keygen (rsa)

Step-1   ssh-keygen  -t  rsa
		Press enter for connect via ssh without passphrase

Step-2  Cross check keys 
	ls  -l  ~/.ssh/

Step-3  Share my public key to known hosts

 ssh-copy-id -i  /root/.ssh/id_rsa.pub  192.168.18.X

Step4:  now you can login  in 192.168.18.36 IP server

	And  cross check your public key  

	ls  -l   /root/.ssh

authorized_keys   

Step5:  Cross check via ssh command

	ssh  192.168.18.36

Your ssh will connect without password
-------------------------------------------------------------------

Step6.  Clear cache of ssh know host (IF YOU WANT)

vim  /root/.ssh/known_hosts

Delete all lines  and exit 


systemctl   restart sshd 
10.2.2021

Todays topic  

	1. at command +   locate   (YOU)

	2. ACL in linux  (access control list) 
		Chmod
Chown

Getfacl
Setefacl
  
		
	
	3. create github account

	4.  install git in centos /  ubuntu
		Key access (  RSA  / ed25519) 
	5. Server







ACL

  mkdir cdts
 getfacl cdts/
 setfacl -m u:john:rw  cdts/
  getfacl cdts/
   setfacl -m g:raj:rwx  cdts/
   getfacl cdts/
  setfacl   -b cdts/
  getfacl cdts/
  setfacl -m u:john:rw  cdts/
  setfacl -m g:raj:rwx  cdts/
  getfacl cdts/
  setfacl   -b cdts/
   getfacl cdts/
 getfacl  cdts/
  setfacl  -m g:raj:rwx  cdts/
  setfacl -x g:raj:  cdts/
 getfacl  cdts/
  setfacl  -m g:raj:rwx  cdts/
  getfacl  cdts/
 setfacl -x  g:raj:  cdts/
  getfacl  cdts/
 getfacl  cdts/
  setfacl -m g:raj:rwx  cdts/
 setfacl -m g:raj:r  cdts/
 getfacl  cdts/
  setfacl   -b cdts/
 getfacl  cdts/
      Revoke permission of specific user in ACL
 setfacl   -x  u:john:  cdts/
   Revoke permission of Specific group in ACL
setfacl -x g:raj:  cdts/
Revoke all (User & Group)
setfacl   -b cdts/

Question 


  history
  cp -v  /etc/fstab   /var/tmp/
  ls  -l  /var/tmp/fstab
  getfacl  /var/tmp/fstab
  su  - alice
  su  - lyne
  getfacl  /var/tmp/fstab
  setfacl   -m u:lyne:rw  /var/tmp/fstab
  getfacl /var/tmp/fstab
  setfacl -m u:maninder:x  /var/tmp/fstab
 getfacl /var/tmp/fstab
setfacl  -m  u:alice:r  /var/tmp/fstab
getfacl  /var/tmp/fstab
 setfacl -m  o::---  /var/tmp/fstab
 getfacl  /var/tmp/fstab


Topic:  
	git  command (Linux / Windows server /Ubuntu) 
	github  (Repo mgmt system)
--------------------------------------------------
	VCS  (Version control system)
	

DevOps 


Git install 

Step-1  Install git 

		Yum install git  -y

Step-2 
 cd  /opt/
  189  mkdir  mylab
  190  cd mylab/
  191  pwd
  192  git config --global user.name "cdtsbikaner"
  193  git config --global user.email "cdtsbikaner@gmail.com"
  194  git  init

Step-3  Sir will add all ed25519 key at github.com


Step-4  clone repo at our laptop

Git clone  git@github.com:cdtsbikaner/learn-devops.git

Step-5   check repo

	Ls -l

Step-6  go to repo directory 

	Cd  learn-devops

Step-7   pull repo data 
		Git pull  
Step-8   check branch name

		Git branch 
Step-9  fetch all data 
		Git  fetch
Step-10  git checkout dev
		Git pull 

