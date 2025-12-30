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

Level 33-34:

This is the final level and does not require solving a challenge.
It confirms successful completion of all Bandit levels.
No additional password is needed.
commands used:
whoami

completion output/solution:
bandit33
