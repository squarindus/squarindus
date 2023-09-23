> # BANDIT CHALLENGES>>>>>
  > LEVEL 0 TO LEVEL 1
 *    The password for the next level is stored in a file called readme located in the home directory.
      Use this password to log into bandit1 using SSH.
      Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
 * In this level we use the basic commands like cat,ls in order to retrive the password from readme file
 * Password=NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
  > LEVEL 1 TO LEVEL 2
 * The password for the next level is stored in a file called - located in the home directory.
 * In Linux, a filename can start with – (dash) or can be just – (dash). Above it is given that the file is called – (dash).
   But content of the file – can not be displayed using command cat – because it reads from standard input and it is waiting for us to type something.
 * To open dashed file cat < -file_name
 * password  :rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
  > LEVEL 2 TO LEVEL 3
 * To open a file having space in file name put a \ before every space in the filename
 * password :aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
  > LEVEL 3 TO LEVEL 4
 * Hidden file accessing using ls -a command
 * cd command is used to change our current working directory. cd is followed by the pathname of the desired working directory.Our 
   current working directory is /home/bandit3 and our desired working directory is /home/bandit3/inhere 
 * password:2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
  > LEVEL 4 TO LEVEL 5
 * To open dashed file cat < -file_name 
 * password:lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
  > LEVEL 5 TO LEVEL 6
 * In order to solve 5th level we use find command.
 * Syntax: find inhere -readable -size 1033c \! -executable
 * password:P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
  > LEVEL 6 TO LEVEL 7
 * The password for the next level is stored somewhere on the server and has all of the following properties:
    * owned by user bandit7
    * owned by group bandit6
    * 33 bytes in size
 * cat /var/lib/dpkg/info/bandit7.password
 * password:z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
  > LEVEL 7 TO LEVEL 8
 * The password for the next level is stored in the file data.txt next to the word millionth
 * Here we can use grep program. grep is used to find text patterns within file. The text we have to find is millionth and the password 
    for next level is next to it.
 * password:TESKZC0XvTetK0S9xNwm25STk5iWrBvP
  > LEVEL 8 TO LEVEL 9
 * The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.
 * Syntax: sort data.txt |uniq -u
 * password:EN632PlfYiZbn3PhVK3XOGSlNInNE00t
  > LEVEL 9 TO LEVEL 10
 * The password for the next level is stored in the file data.txt in one of the few human-readable strings, beginning with several ‘=’ 
    characters.
 * Syantax: strings data.txt |grep '='
 * password:G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
  > LEVEL 10 TO LEVEL 11
 * The password for the next level is stored in the file data.txt, which contains base64 encoded data.
 * Syntax: cat data.txt |base64 --decode
 * passwords:JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
  > LEVEL 11 TO LEVEL 12
 * The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been 
   rotated by 13 positions.
 * Copied the text rotated by 13 positions and use cipher unlocker inorder to get the passsword.
 * passwords:JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
  > LEVEL 12 TO LEVEL 13
 * The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly 
    compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir.
 * Syntaxes....
   * mkdir /tmp/myname123
   * cp data.txt /tmp/pc
   * mv data.txt myname123
   * xxd -r myfile.txt > myfile1.bin
   * zcat myfile1.bin > myfile2
   * bzcat myfile2 > myfile3
   * tar -xvf myfile4
   * cat myfile9
 * password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
  > LEVEL 13 TO LEVEL 14
 * The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you 
   don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname 
   that refers to the machine you are working on.
 * cat /etc/bandit_pass/bandit14
 * password:fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
  > LEVEL 14 TO LEVEL 15
 * The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
 * Syntaxes..
   * scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
   * netcat localhost 30000
 * password:fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
  > LEVEL 15 LEVEL 16
 * The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL 
   encryption.
 * Syntax: openssl s_client -connect localhost:30001
 * Enter the password for the current Level.
 * password:JQttfApK4SeyHwDlI9SXGR50qclOAil1
  > LEVEL 16 TO LEVEL 17
 * The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the 
   range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and 
   which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to 
   it.
 * We found two ports and port 31790 is open. Open port means server on that port is listening.
 * Now to connect to port 31790 use openssl with s_client tool, which  have done in previous challenge.
 * Syntaxes...
   * nmap -sV localhost -p 31000-32000
   * openssl s_client -connect 31790
   * mkdir /tmp/bandit166
   * cd /tmp/bandit166
   * nano.ssh.private
   * -----BEGIN RSA PRIVATE KEY-----
    MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
    imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
    Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
    DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
    JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
    x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
    KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
    J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
    d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
    YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
    vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
    +TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
    8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
    SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
    HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
    SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
    R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
    Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
    R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
    L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
    blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
    YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
    77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
    dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
    vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
     -----END RSA PRIVATE KEY-----
   * ls
   * chomod 400 sshkey.private
   * ls -hal
   * ssh -i sshkey.private bandit17@localhost -p2220
   * password comm: cat /etc/bandit_pass/bandit17
 * password:VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
  > LEVEL 17 TO LEVEL 18
 * There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between 
   passwords.old and passwords.new
 * Syntax: diff passwords.old passwords.new
 * password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
  > LEVEL 18 TO LEVEL 19
 * The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.
 * However we an bypass the code to get the password .
 * We receive Byebye ! as the output. In the question it is mentioned that someone has modified .bashrc to log you out when you log in with SSH.
   With option -t in ssh command we can force psuedo-tty allocation.
   “Pseudo Terminals” emulates Terminal hardware, handling input and output in the same way a physical device would so that the software connected is not aware there’s not a real device 
   attached.We have forced a psuedo terminal and we know that password is in the readme file, so we can view password using command.
 * Syntax: ssh -t bandit18@bandit.labs.overthewire.org -p 2220 cat readme
 * password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
  > LEVEL 19 TO LEVEL 20
 * To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be 
   found in the usual place (/etc/bandit_pass), after you have used the setuid binary.
 * Setuid, which stands for set user ID on execution, is a special type of file permission in Unix and Unix-like operating systems such as Linux and BSD. It is a security tool that 
   permits users to run certain programs with escalated privileges.When an executable file’s setuid permission is set, users may execute that program with a level of access that matches 
   the user who owns the file.
 * Syntax: ./bandit20-do cat /etc/bandit_pass/bandit20
 * password:VxCazJaVykI6W36BkBU0mJTCM8rR95XT
  > LEVEL 20 TO LEVEL 21
 * There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of 
   text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
 * Binary file suconnect has escalated privilege as user bandit21. After running command ./suconnect it shows how to use command i.e. Usage: ./suconnect It also shows “This program will 
   connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back”.
 * Syntaxes..
    * echo -n 'VxCazJaVykI6W36BkBU0mJTCM8rR95XT' | nc -l -p 1234 &
    * ./suconnect 1234 cat /etc/bandit_pass/bandit21
 *  password:NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
  > LEVEL 21 TO LEVEL 22
 * In directory /etc/crond.d/, file important to us is cronjob_bandit22. It is a crontab file and contain commands. The content can be viewed using cat cronjob_bandit22.
 * The command is executing the file cronjob_bandit22.sh which is in the directory /usr/bin/. Lets see the content of file cronjob_bandit22.sh using command 
   cat/usr/bin/cronjob_bandit22.sh.
 * cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
 * password:WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
  > LEVEL 22 TO LEVEL 23
 * A program is running automatically at regular intervals from cron, the time-based job scheduler.
 * Look in /etc/cron.d/ for the configuration and see what command is being executed.
 * Syntaxes..
    * ls /etc/cron.d/
    * cat cronjob_bandit23
    * /usr/bin/cronjob_bandit23.sh
    * echo I am user $myname | md5sum | cut -d ' ' -f 1+
    * cat /tmp/8ca319486bfbbc3663ea0fbe81326349
  * password:QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
  > LEVEL 22 TO LEVEL 23
 * A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and 
   see what command is being executed.
 * The line to create the filename inputs the string “I am user bandit23” into md5sum, which will return the md5 hash from the string. The last 
   instruction removes everything after the space. You can test out for yourself what it would look like without this line.
 * Syntaxes:
    * ls /etc/cron.d/
    * cat cronjob_bandit23
    * /usr/bin/cronjob_bandit23.sh
    * echo I am user $myname | md5sum | cut -d ' ' -f 1
    * at /tmp/8ca319486bfbbc3663ea0fbe81326349
 * password:QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
  > LEVEL 23 TO LEVEL 24
 * A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and 
   see what command is being executed.
 * Syntaxes
    * touch /tmp/getpswd.sh
    * vim /tmp/getpswd.sh
    * chmod 777 /tmp/getpswd.sh
    * touch /tmp/s8n.txt
    * chmod 666 /tmp/s8n.txt
    * cp /tmp/getpswd.sh /var/spool/bandit24/foo
    * cat /tmp/s8n.txt
 * password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
  > LEVEL 24 TO LEVEL 25
 * A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit 
   pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
   You do not need to create new connections each time.
 * Syntaxes
    * vim brute_force.sh
    * You need to brute force the bash file to the shell.
    * chmod +x brute_force.sh
    * ./brute_force.sh
    * ls
    * sort result.txt | grep -v "Wrong!"
 * password:p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
  > LEVEL 25 TO LEVEL 26
 * 
 



    


   
   
   
   
