# OverTheWire Bandit Challenges By:Kiran S Pillai
 
>## _Aim of the challenge is to get the insights about the fundamentals of Linux/UNIX environment and the real time use of Linux commands. Basically the game starts with the level 0, each level conists of passwords hidden some where in the server, using the hints and the linux commands we have to find it and proceed to the next level._
## 
#
## **LEVEL 0**
>To login to the game using _**SSH**_ and connect to the host **bandit.labs.overthewire.org** on port-**2220** using the **username: bandit0** and **password: bandit0** 

* _ssh: ( to login into the server type "ssh < username > @ < host > -p < port > )_
___
## **LEVEL 0 --> 1**
>_LEVEL GOAL_   
The password for the next level is stored in a file called **readme** located in the home directory.

* Using the **ls** command we list out all the files in the current directory.
* Then using the **cat readme** command we access the readme file and retrieve the password.  
>>**PASSWORD OBTAINED =** boJ9jbbUNNfktd78OOpsqOltutMc3MY1
___
## **LEVEL 1 --> 2**
>_LEVEL GOAL_   
The password for the next level is stored in a file called **-** located in the home directory

* Using the **ls** command we list out all the files in the current directory.
* Since the file name is a special character we use the **cat ./-** command and retrieve the password.  

![Alt text](https://i.ibb.co/5nzwzfr/bandit-1.png "")
>>**PASSWORD OBTAINED =** CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
___
## **LEVEL 2 --> 3**
>_LEVEL GOAL_  
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

* Using the **ls** command we list out all the files in the current directory.
* Then using the **cat spaces\ in\ this\ filename** command we access the readme file and retrieve the password. Here the \ denotes tht the spaces are the part of file name.
>>**PASSWORD OBTAINED =** UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
___
## **LEVEL 3 --> 4**
>_LEVEL GOAL_  
The password for the next level is stored in a **hidden file** in the **inhere** directory.

* Using the **ls** command we list out all the files in the current directory.
* Then using the **cd inhere** command we access inhere directory.
* Then **cat .inhere** command will allow us to retrieve the password from the hidden file.
>>**PASSWORD OBTAINED =** pIwrPrtPN36QITSp3EQaw936yaFoFgAB
___
## **LEVEL 4 --> 5**
>_LEVEL GOAL_  
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

* Using the **ls** command we list out all the files in the current directory.
* Then using the **cd inhere** command we access inhere directory.
* Then **ls** command will list out all the files in that directory.
* Then __files ./*__ command will list out all the files with their respective datatypes.
* Using **cat ./-file07** will help to retrieve the password.
>>**PASSWORD OBTAINED =** koReBOKuIDDepwhWk7jZC0RTdopnAYKh
___
## **LEVEL 5 --> 6**
>_LEVEL GOAL_  
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:  
human-readable,  
1033 bytes in size,  
not executable.  

* Using the **ls** command we list out all the files in the current directory.
* Then using the **cd inhere** command we access inhere directory.
* Then **find . -type f -size 1033c ! -executable** command will seearch for the file with specified properties.

* Then **cat ./maybehere07/.file2** command will allow us to retrieve the password.
>>**PASSWORD OBTAINED =** DXjZPULLxYr17uwoI01bNLQbtFemEgo7
___
## **LEVEL 6 --> 7**
>_LEVEL GOAL_  
The password for the next level is stored somewhere on the server and has all of the following properties:  
owned by user bandit7  
owned by group bandit6  
33 bytes in size.

* Using the **find / type f -user bandit7 -group bandit6 -size 33c** command we list out all the files in the current directory with the specified property.
* From the listed out files we can we see a file named as **/var/lib/dpkg/info/bandit7.password** which contains the password.
* Then **cat /var/lib/dpkg/info/bandit7.password** command will allow us to retrieve the password.
>>**PASSWORD OBTAINED =** HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
___
## **LEVEL 7 --> 8**
>_LEVEL GOAL_  
The password for the next level is stored in the file data.txt next to the word millionth.

* Using the **ls** command we list out all the files in the current directory.
* Then **cat data.txt** command will show the strings in the file data.txt.
* Using strings command we can sort and get the required file.
* **strings data.txt | grep "millionth"** will show the file with password.
>>**PASSWORD OBTAINED =** cvX2JJa4CFALtqS87jk27qwqGhBM9plV
___
## **LEVEL 8 --> 9**
>_LEVEL GOAL_  
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.

* Since it is said that password is contained in the file data.txt we will directly access the file.
* **cat data.txt** command will show the strings in the file data.txt.
* Using sort command we can sort and get the string which is occurs only ones.
* **sort data.txt | uniq -c** will show the line of text with password.
>>**PASSWORD OBTAINED =** UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
___
## **LEVEL 9 --> 10**
>_LEVEL GOAL_  
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

* Since it is said that password is contained in the file data.txt we will directly access the file.
* **strings data.txt | grep "="** command will show the strings containing "=" from the file data.txt.
>>**PASSWORD OBTAINED =** truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
___
## **LEVEL 10 --> 11**
>_LEVEL GOAL_  
The password for the next level is stored in the file data.txt, which contains base64 encoded data.

* Since it is said that password is contained in the file data.txt which is base64 encoded.
* we use **base64 -d data.txt**
>>**PASSWORD OBTAINED =** IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
___
## **LEVEL 11 --> 12**
>_LEVEL GOAL_  
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

* Since it is said that password is contained in the file data.txt.
* **cat data.txt** we get the string where the letters are rotated by 13 positions.
* Then using **cat data.txt | tr a-zA-Z n-za-mN-ZA-M** we obtain the original string.
>>**PASSWORD OBTAINED =** 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
___
## **LEVEL 12 --> 13**
>_LEVEL GOAL_  
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!) 

* Using **mkdir /tmp/kirk** we create a directory.
* To copy data into kirk **cp data.txt /tmp/kirk**.
* **cd /tmp/kirk** is used to access the directory.
* **ls** to check the if the directory contains data.txt.
* **xxd -r data.txt > data** Reverts thr hexdump value to its binary form and send the value to the file data.
* **file data** shows that he file is gzip comressed data.
* **mv data file.gz** This will change the file type to gzip.
* **gzip -d file.gz** decompresses the file.
* When file becomes POSIX tar archive(GNU) we change the file type to file.tar.
* Extracting the data from thr file can be done using **tar xf file.tar**
* After similar successfull uncomrpresssing and changing the file type  will lead us to a file wth ASCII text.
* **cat data** will result in password.  

![ALt text](https://i.ibb.co/sy3ZbqT/badit-12.png "screenshot of the terminal")
![](https://i.ibb.co/8Prm0kt/badit-12-1.png "screenshot of the terminal")
>>**PASSWORD OBTAINED =** 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

___
## **LEVEL 13 --> 14**
>_LEVEL GOAL_  
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

* Using the **ls** command we get the **sshkey.private** file. 
* Since the file can only accessed by the bandit14 user we use the ssh command **ssh -i sshkey.private bandit14@localhost** (-i refers to identity file).
* It was mentioned that the password is stored in /etc/bandit_pass/bandit14, **cat /etc/bandit_pass/bandit14**  will  retrieve the pasword.
>>**PASSWORD OBTAINED =** 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
___
## **LEVEL 14 --> 15**
>_LEVEL GOAL_  
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

* We are already in the logged into bandit14 thru previous level.
* So using netcat command we can retrieve password by submitting the pasword of previous level **nc localhost 30000**  and **4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e**  

![](https://i.ibb.co/dQsNVhS/bandit14-15.png "screenshot of the terminal")
>>**PASSWORD OBTAINED =** BfMYroe26WYalil77FoDi9qh59eK5xNr
___
## **LEVEL 15 --> 16**
>_LEVEL GOAL_  
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

* Using the **ncat --ssl localhost 30001** command we can connect new port and submit the previous password to get the new password.  

![](https://i.ibb.co/7kykS9Z/bandit-15-16.png "screenshot of the terminal")
>>**PASSWORD OBTAINED =** cluFn7wTiGryunymYOu4RcffSxQluehd
___
## **LEVEL 16 --> 17**
>_LEVEL GOAL_  
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

* Using  **nmap localhost -p 31000-32000** will show us the active/listening servers.
* Then by using **ncat --ssl localhost < port >** command we will find which one speaks ssl by passing the previously obtained password, the wrong port will return what we send or get error.
* The right port gave back a long text, which is private key.
* This private key can be directly used for the next level, for that we have to save that in a file in home directory.
* Using **vim < file name >** ( ex: vim key) we open up a text editor where we paste the private key and save it.
*  Since this an open port to protect the private key, we make it only accessable to the user by using **chmod 400** which keeps it protected.
* Then using **ssh -i key bandit17@bandit.labs.overthewire. org -p 2220** we can login to bandit level 17.

![](https://i.ibb.co/6r7N59g/bandit-16-1.png "screenshot of the terminal")
![](https://i.ibb.co/pd3vzGJ/bandit-16-2.png "screenshot of the terminal")
___
## **LEVEL 17 --> 18**
>_LEVEL GOAL_  
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

* Using the **diff  passwords.old passwords.new** command we get the only line that is changed between those two files. 
* With this password we can login to next level.
>>**PASSWORD OBTAINED =** kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
___
## **LEVEL 18 --> 19**
>_LEVEL GOAL_  
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

* Using the **ssh -t bandit18@bandit.labs.overthewire.org -p2220 /bin/sh** command it forces a psuedo terminal allocation which helps in overriding the bash.rc which was logging out us automatically.
* Once logged in, using **ls** we can list the files in it.
* It contains a **readme** which can be accessed using **cat readme** command and password is retrieved.
>>**PASSWORD OBTAINED =** IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
___
## **LEVEL 19 --> 20**
>_LEVEL GOAL_  
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

* After logging into the level 19.
* Using the **ls** command we can list the files in the directory.
* As per the instruction we are not allowed to passs any arguements, so using **./bandit20-do** command will result in 
 (Run a command as another user. Example: ./bandit20-do id)
* Therefore it was already mentioned that the password is stored in (/etc/bandit_pass) , thus using the command **./bandit20-do cat /etc/bandit_pass/bandit20** will help us retieve the password.
>>**PASSWORD OBTAINED =** GbKksEFF4yrVs6il55v6gwY5aVje5f0j
___
## **LEVEL 20 --> 21**
>_LEVEL GOAL_  
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

* In this level we require two sesions. So we login into to level 20 from both the terminal.
* In the secondary terminal this command is given **cat /etc/bandit_pass//bandit20 | nc localhost -p 1234**,
* And the main terminal we run the command **./suconnect 1234**,( Read: GbKksEFF4yrVs6il55v6gwY5aVje5f0j-
Password matches, sending next password)
* Now the password for the next level will be available in the second terminal that we created.  

![](https://i.ibb.co/YR0g5NW/bandit20.png "screenshot of the terminal" )
>>**PASSWORD OBTAINED =** gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
___
## **LEVEL 21 --> 22**
>_LEVEL GOAL_  
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

* Using this command **ls /etc/cron.d/** we can look into the directory for files.
*  From the listed files twe expect the password to be in a file named cronjob_bandit22 , hence **cat /etc/cron.d/cronjob_bandit22** command will reboot and run the shell script **/usr/bin/cronjob_bandit22.sh**.
* Now examining the shell script will result in opening a file and dumping the password for level 22 into that file.
* So using **cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv** we will recieve the password.
>>**PASSWORD OBTAINED =** Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI
___
## **LEVEL 22 --> 23**
>_LEVEL GOAL_  
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

*  **ls /etc/cron.d/** to check the content of the file.
* **cat /etc/cron.d/cronjob_bandit23** will access that particular file. #!/bin/bash  
myname=  (whoami )
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
cat /etc/bandit_pass/$myname > /tmp/$mytarget
*  Since variable myname is is null we give command **myname=bandit23** this will assign bandit23 to varibale myname.
* Now excuting the command **echo I am user $myname | md5sum | cut -d ' ' -f 1** we will get a text "8ca319486bfbbc3663ea0fbe81326349".
* Accessing the path **cat /tmp/8ca319486bfbbc3663ea0fbe81326349** will get us the password.
>>**PASSWORD OBTAINED =** jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n
___
## **LEVEL 23 --> 24**
>_LEVEL GOAL_  
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!
NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

*  **cd /etc/cron.d/** to get into the directory.
*  **ls** to check the content of the directory.
* **cat cronjob_bandit24** will access that particular file.  
`#!/bin/bash`  
`myname=$(whoami)`  
`cd /var/spool/$myname`  
`echo "Executing and deleting all scripts in /var/spool/$myname:" `  
`for i in * .*;  `  
`do`  
`if [ "$i" != "." -a "$i" != ".." ];`  
`then`  
`echo "Handling $i"`  
`owner="$(stat --format "%U" ./$i)"`  
`if [ "${owner}" = "bandit23" ]; then`  
`timeout -s 9 60 ./$i`  
`fi`  
`rm -f ./$i`  
`fi`
`done`

*  Using this command we create directory in tmp **mkdir /tmp/kirkiosk**.
* Now we access the directory **cd /tmp/kirkiosk** and we create an excutable file in it using the command **vim passkirk.sh**
* (#!/bin/bash  
cat /etc/bandit_pass/bandit24 > /tmp/kirkiosk/passwd.txt) will be written inside the executable file.
* Using the **chmod 777** we will change the permissions for the directory and the executable.
* Now we need copy the files to the bandit24, for that we use command **cp passkirk.sh /var/spool/bandit24/passkirk.sh**
* After one minute we get the passwd.txt file dumped into the current directory and using **cat passwd.txt** we get the password for the next level.

![](https://i.ibb.co/SxLqQD2/bandit-23.png "screenshot of the terminal")
>>**PASSWORD OBTAINED =** UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ
___
## **LEVEL 24 --> 25**
>_LEVEL GOAL_  
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

*  **mkdir /tmp/cake** to create a directory.
*  **cd /tmp/cake** to get into the directory.
* **nc localhost 30002** using this command we check the port.
* **vim brute.sh** to creat an executable file using the text editor.  
`#!/bin/bash`  
`bandit24=UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ`  
`for pin in {0000..9999}; do`  
`echo "$bandit24 $pin"`  
`done | nc localhost 30002`
* Using the **chmod 777** we will change the permissions for the executable.
* Now we call the executable **./brute.sh**.
* After many wrong attempts the pin matches and we get the password for the next level. 

![](https://i.ibb.co/N6gL1Jy/bandit-24-1.png "screenshot of the terminal")
![](https://i.ibb.co/YTPMFvS/bandit-24-2.png "screenshot of the terminal")
>>**PASSWORD OBTAINED =** uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG
___
## **LEVEL 25 --> 26**
>_LEVEL GOAL_  
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

*  After connecting login into the bandit25 we check for the available files using **ls** command. Which results in "bandit26.sshkey" file.
*  Opening that file using **cat bandit26.sshkey** will result in a "RSA PRIVATE KEY".
* **ssh bandit26@localhost -i bandit26.sshkey** we try logging into the bandit26 using this RSA private key, but it prints bandit26 in an art form and  prints "Connection to localhost closed." after this message we are kicked out again.
* Since it was mentioned that the shell user isnt [/bin/bash], so to check that we use this command **cat /etc/passwd** and we find out that it has "/usr/bin/showtext" as its shell.  
![](https://i.ibb.co/jMFHbZw/bandit25-1.png  "screenshot of the terminal")
* Now **cat /usr/bin/showtext** will show the contents of the shell.  
`#!/bin/sh`  
`export TERM=linux`  
`more ~/text.txt`  
`exit 0` 
(Here the `more` command will show the ASCII art that is in the `text.txt` file and immidiately exits.)
* The more command shows one page at a time. So we resize our terminal window such that the ASCII art is just partially visible. 
* While the shell is still running we open the text editor by pressing "v" , now while in text editor we run the command **:r /etc/bandit_pass/bandi26** , this will show us the password and we can exit the level.  
![](https://i.ibb.co/LRCNLs8/bandit25.png "screenshot of the terminal")

>>**PASSWORD OBTAINED =** 5czgV9L3Xx8JPOyRbXh6lQbmIOWvPT6Z
___
### _Thank you_
___-KSP___
 
