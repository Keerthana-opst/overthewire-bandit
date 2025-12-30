Level 9-10:

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.
sort data.txt: The sort command is used to sort the lines in a text file. In this case, it's sorting the lines in the file data.txt. After execution, the lines in data.txt will be sorted in lexicographic (alphabetical) order.

 (pipe): The pipe symbol | is used to redirect the standard output (stdout) of the command on its left to the standard input (stdin) of the command on its right. In this case, it pipes the sorted output from sort data.txt to the next command, uniq -c.

uniq -c: The uniq command is used to filter out duplicate lines from a sorted input. The -c option is used to count the number of occurrences of each unique line. In this case, it will provide a count of how many times each line appears in the sorted data.

(pipe): Another pipe is used to redirect the output from uniq -c to the next command, grep "1 ".

exactly 1.

<img width="902" height="117" alt="image" src="https://github.com/user-attachments/assets/ad20fb30-9d61-4495-b6be-483c435ff917" />

Level 10-11:

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

cat data.txt: The cat command is used to concatenate and display the contents of the file named data.txt. It reads the content of the file and sends it to the standard output (usually your terminal).

(pipe): The pipe symbol | is used to redirect the standard output (stdout) of the command on its left to the standard input (stdin) of the command on its right. In this case, it pipes the output of cat data.txt as input to the next command, strings.

strings: The strings command is used to extract human-readable text from binary files or data. It scans the input data for sequences of printable characters and displays them.

grep ^=: The grep command is used to search for patterns in text. In this command, it searches for lines that start with the = character.


<img width="823" height="782" alt="image" src="https://github.com/user-attachments/assets/2fead395-1fe4-4962-80ec-36669ed5ea86" />

Level 11-12 :

The password for the next level is stored in the file data.txt, which contains base64 encoded data. Base64 encoding is a method of encoding binary data, such as files or non-text data, into a text-based format. It is commonly used in computing and data transmission to represent binary data as ASCII text, making it easier to store, transfer, and display data in systems that expect text. Key features of Base64 encoding include:

Character Set: Base64 encoding typically uses the characters A-Z, a-z, 0-9, along with two additional characters (usually '+ and '/), which are used to represent the 64 possible values (hence "Base64").

URL-safe Base64: To accommodate URL parameters and avoid potential encoding conflicts, URL-safe Base64 replaces '+' with '-' and '/' with '_'.


<img width="927" height="766" alt="image" src="https://github.com/user-attachments/assets/2fae41bc-1fef-4f9f-8bf6-3c5ae9a4c0a8" />

Level 12 → Level 13 :

Level Goal:
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed.. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)
Commands you may need to solve this level:
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file


<img width="635" height="753" alt="image" src="https://github.com/user-attachments/assets/9175a8e5-28bc-4c32-b19c-b69e269ef20c" />


Level 13 → Level 14:

Level Goal:
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on
Commands you may need to solve this level:
ssh, telnet, nc, openssl, s_client, nmap

Solution:
<img width="520" height="71" alt="image" src="https://github.com/user-attachments/assets/44eb8e9f-59b7-47be-aba7-d8f00cab6f55" />
 will be logged in as user bandit14 :
<img width="441" height="83" alt="image" src="https://github.com/user-attachments/assets/5847ebed-27cb-44a6-98fc-39b6418ae002" />

Level 14 → Level 15:

Level Goal:
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
Commands you may need to solve this level:
ssh, telnet, nc, openssl, s_client, nmap
Prerequisite to solve this challenge:
You need to know:
nc command to start a TCP connection

Solution:
<img width="357" height="157" alt="image" src="https://github.com/user-attachments/assets/d99cd62f-3210-43eb-8730-3e0d118238b3" />

Bandit Level 15:

Level Goal:
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.
Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…
Commands you may need to solve this level:
ssh, telnet, nc, openssl, s_client, nmap
Prerequisite to solve this challenge:

Solution:
<img width="540" height="158" alt="image" src="https://github.com/user-attachments/assets/d1d2c774-91fa-455f-9600-3823066b8348" />

<img width="373" height="197" alt="image" src="https://github.com/user-attachments/assets/fd909b30-3692-41cb-b849-4b4a17a668b8" />

Bandit Level 16 - 17:

Level Goal:
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
Commands you may need to solve this level:
ssh, telnet, nc, openssl, s_client, nmap
Prerequisite to solve this challenge:
You need to know:
What is a port scanner? What is it used for?
nmap command

solution :
nmap -sV = port scan and determine the name of found services and their version.
-p 31000–32000 = port range from 31000 to 32000
Connect to service on port 31790 using openssl command like previous level
Once connected, paste in bandit16’s password
You’ll get an SSH private key:
Connect to service on port 31790 using openssl command like previous level
Once connected, paste in bandit16’s password
You’ll get an SSH private key:


<img width="562" height="363" alt="image" src="https://github.com/user-attachments/assets/81d27280-6fae-48c5-b598-f16180067d3d" />

Create a temporary folder using mkdir command
Create a file using nano command and paste the private key in it
Change the privatekey file permission to read only to avoid too open error when connect to bandit17 using SSH:
Once logged in as bandit17, cat the password
Answer is : xLYVMN9WE5zQ5vHacb0sZEVqbrp7nBTn


<img width="434" height="84" alt="image" src="https://github.com/user-attachments/assets/ea63bd5e-00eb-42ca-a317-c9785a0a001d" />

Level 17 -18:

Level Goal:
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new
Commands you may need to solve this level:
cat, grep, ls, diff
Prerequisite to solve this challenge:
diff command

Solution:

<img width="455" height="206" alt="image" src="https://github.com/user-attachments/assets/cf982f77-0190-4fc4-808d-450191acaa28" />

Level 18 - Level 19:

Level Goal:
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.
Commands you may need to solve this level:
ssh, ls, cat
Prerequisite to solve this challenge:
You need to know how to write command at the same time with ssh.

Solution:
run: ssh bandit18@bandit.labs.overthewire.org -p 2220 ls
You will get a readme file and kicked out right away
run: ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
You will get the password.
