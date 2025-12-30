Level 19 - Level 20:

Level Goal:
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.
Prerequisite to solve this challenge:
You need to know:
What is effective user? (It is basically the current user)
whoami command to check effective user

Solution:
Execute the given binary file in order to become bandit20 user and read the password:

<img width="542" height="172" alt="image" src="https://github.com/user-attachments/assets/c7ebbba6-b390-4e31-bc98-97dc568f27d6" />

Level 20 - Level 21:

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
Commands you may need to solve this level:
ssh, nc, cat, bash, screen, tmux, Unix ‘job control’ (bg, fg, jobs, &, CTRL-Z, …)
Prerequisite to solve this challenge:
You need to know:
nc command to set up a TCP server
tmux to open multiple screen of the same user.
run tmux
Once you press enter, you’ll see a green bar at the buttom (you are having one window now, create another using ctrl+b then press c):


<img width="273" height="157" alt="image" src="https://github.com/user-attachments/assets/b6ff927a-8ef9-40d7-a53e-cda1601f1f7b" />


You can navigate between those 2 windows using ctrl+b then press a number
On one screen, make a TCP server
On another screen, execute suconnect file and give the port number (ex: 41815) as the argument
You’ll see a connection message at the server screen like below
At the server side, send the password of the last level back to the client
And you’ll get reply back as a new password.

<img width="489" height="152" alt="image" src="https://github.com/user-attachments/assets/2fc9a4e3-0c15-4a26-9638-53a3b3d71501" />

Level 22-23:

A cron job runs a script automatically as bandit23.
The script reads the password and writes it to a predictable file in /tmp.
Reading that file reveals the password.
commands used :
cat /etc/cron.d/cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
cat /tmp/<generated_filename>

solution:
<bandit23_password>

Level 24-25:

A local service requires the correct password and a 4-digit PIN.
Brute-forcing all PIN combinations using a loop and netcat reveals the valid one.
The correct attempt returns the next password.
commands used:
for i in {0000..9999}; do
  echo "<bandit24_password> $i" | nc localhost 30002
done

solution:
Correct!
The password of bandit25 is <bandit25_password>

Level 26-27:

The shell is restricted and exits immediately after login.
Launching vi allows escaping the restricted shell by spawning /bin/bash.
This gives access to read the next password.
commands used:
ssh bandit26@bandit.labs.overthewire.org -p 2220 "vi"
:set shell=/bin/bash
:shell
cat /etc/bandit_pass/bandit27

solution:
<bandit27_password>

Level 28-29:

The password was removed in a Git commit but still exists in history.
Inspecting previous commits reveals the deleted secret.
Git history analysis exposes the password.
commands used:
git clone ssh://bandit28-git@localhost/home/bandit28-git/repo
cd repo
git log
git show <commit_id>

solution:
<bandit29_password>
