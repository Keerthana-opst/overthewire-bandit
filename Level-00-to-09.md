OverTheWire Bandit Writeups (Levels 0–34)
Level-00-to-09.md

Level 0-1:

This level involves logging into the game using SSh command 

<img width="966" height="546" alt="image" src="https://github.com/user-attachments/assets/ce061572-000b-40c6-968a-f2c6d6329a7f" />


SSH ,which stands for secure shell, is a cryptographic network protocal used for securely connecting to and managing remote servers and devices over an unsecuresd network .it provides a secure , encrypted method for logging into and executing commands on a remote machine ,as well as for securing file transfer .SSH is widely used for various purposes,including system administration ,remote acess, secure data transfer . the host we need to connect is bandit.labs.overthewire.org on port 2220 .the username is bandit0 and the password is bandit0.

Level 1-2:

The password to this level is stored in the readme file in the home directory.


<img width="679" height="173" alt="image" src="https://github.com/user-attachments/assets/7bb062a7-2c02-4bf8-8aff-882c13d01878" />

Level 2-3:

The password to this level is stored in a file called -located in the home directory of the system. ./ is used to specify the current directory .this ensures that the - is treated as a file in the current directory .

. is the name of the file that needs to be read

<img width="674" height="175" alt="image" src="https://github.com/user-attachments/assets/0c42165e-8217-476b-a70d-f11719702aa2" />

Level 3-4:

The password to the level is stored in a file called spaces in the filename located in the home directory.in this example,the backslashes are used to escape the spaces in the filename , allowing you to read the file without needing quatation marks.


<img width="673" height="199" alt="image" src="https://github.com/user-attachments/assets/a811b6eb-aac8-44c0-b9e2-3a635e25b933" />

Level 4-5:

The password to this level is in a hidden file in the inhere directory.hidden files in unix-like operating systems are typically files whose filename start with a dot(.) character.
these files are hidden in the sense that they are not displayes when you use common commands to list files or directories,such as ls.they are often used to store or configure or metadata information that os not meant to be directly accessed by users .to locate hidden files,you can us the -a or --all option with the ls command ,which instructs ls to show hidden files in the listing.


<img width="672" height="150" alt="image" src="https://github.com/user-attachments/assets/16cd2580-88fd-4755-a4f6-42549ccf94fd" />

Level 5-6:

The password for the nest level is stored in the only humar-readable file in the inhere directory file; this is the file command ,a unix-like utility used to determine and display infromation about the type of a file.

./:This represents the current directory .in unix-like systems,./ is a shorthand notaion for the current working directory . in thos context ,it tells the file command to look for the specified files in the current directory.

-file0*: This is a pattern used files in the current directory .the pattern -file0* indicates that you want to match files that start with -file0 and can have any characters after that.

The asterisk * is a wildcard that matches any number of characters. So, this pattern matches filenames like -file01, -file02, and so on. Putting it all together, the file ./-file0* command checks the file type of all files in the current directory whose names start with -file0. The file command will return information about the type of each matched file, which could be things like text, binary, image, or various other file types. This is useful when you want to quickly identify the file types in a directory, especially if you're dealing with a mix of file formats.


<img width="787" height="161" alt="image" src="https://github.com/user-attachments/assets/c9f76be1-5aa2-49da-91a4-0aee88b408b6" />

Level 7-8:

The password for the next level is stored somewhere on the server and has all of the following properties:owned by user bandit7, owned by group bandit6, 33 bytes in size The find command is again utilized to solve this level.

/: This is the starting directory for the search. In this case, / represents the root directory, which means the search will begin at the root of the file system and traverse through all directories.

-type f: This is a test condition for find that specifies you're looking for files (not directories). The -type f option filters out directories and selects only regular files.

-size 33c: This is a test condition for find that specifies the size of the files to search for. In this case, it's looking for files with a size of 33 bytes. The c indicates that the size is measured in bytes.

-group bandit6: This is a test condition for find that filters files based on their group ownership. It selects files that belong to the group named "bandit6."

-user bandit7: This is another test condition for find that filters files based on their user ownership. It selects files that are owned by the user named "bandit7."


<img width="1037" height="510" alt="image" src="https://github.com/user-attachments/assets/e09e5353-16ae-4afe-b9b4-369be09c1818" />

Level 8-9:

The password for the next level is stored in the file data.txt next to the word millionth.

cat data.txt: The cat command is used to concatenate and display the contents of one or more files. In this case, it is used to display the contents of a file named data.txt. data.txt is the input file for this command, and cat will display its content to the standard output (usually your terminal).

| (pipe): The pipe symbol | is used to redirect the standard output (stdout) of the command on its left to the standard input (stdin) of the command on its right. In this case, it pipes the output of cat - data.txt as input to the next command, grep.

grep millionth: The grep command is used to search for patterns in text. In this command, it searches for the word "millionth" within the text received from cat data.txt. If "millionth" is found within the text, grep will display the lines containing that word.


<img width="912" height="187" alt="image" src="https://github.com/user-attachments/assets/2c648c3b-1b21-4cac-9c4f-5d81f893d256" />

