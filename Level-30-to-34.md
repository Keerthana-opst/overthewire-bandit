Level 30 - 31:

This level involves a Git repository where no changes appear in the working tree.
The password exists as a hidden Git tag, not in the files.
Inspecting tags reveals the stored secret.
commands used:
git clone ssh://bandit30-git@localhost/home/bandit30-git/repo
cd repo
git tag
git show secret

solution:
<bandit31_password>

<img width="1193" height="90" alt="image" src="https://github.com/user-attachments/assets/c3ece7d5-33f0-4a4a-878e-a5c47c1eaba2" />


Level 31-32:

The password is stored in a file that Git is configured to ignore.
By force-adding the ignored file, its contents can be accessed.
This exposes the next password.
commands used:
git clone ssh://bandit31-git@localhost/home/bandit31-git/repo
cd repo
cat README.md
git add -f key.txt
cat key.txt

solutions:
<bandit32_password>

<img width="515" height="528" alt="image" src="https://github.com/user-attachments/assets/68c17c05-1048-4d5e-8399-95bb50a5874e" /> 

Level 32-33:

The shell behaves unexpectedly by converting commands to uppercase.
Using $0 executes the current shell directly, bypassing the restriction.
This restores normal command execution.
commands used:
$0
whoami
cat /etc/bandit_pass/bandit33

solution:
<bandit33_password>

<img width="649" height="111" alt="image" src="https://github.com/user-attachments/assets/fb341d6d-084b-41b8-897e-10cc5538a5a0" />


Level 33-34:

This is the final level and does not require solving a challenge.
It confirms successful completion of all Bandit levels.
No additional password is needed.
commands used:
whoami

completion output/solution:
bandit33

<img width="550" height="267" alt="image" src="https://github.com/user-attachments/assets/736903e0-c90a-4f8f-883e-c20ba02c3845" />
