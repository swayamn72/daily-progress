# OverTheWire: Bandit Progress

## Completed Levels:

### Bandit Level 0 → Level 1
- Used SSH to connect to the Bandit server with the provided credentials.

### Bandit Level 1 → Level 2
- Used `cat` to read the password file in the home directory.

### Bandit Level 2 → Level 3
- Used `cat` to read a file with spaces in its name by enclosing it in quotes or using escape characters.

### Bandit Level 3 → Level 4
- Used `ls -a` to find a hidden file and `cat` to read the password.

### Bandit Level 4 → Level 5
- Used `ls -l` to check file permissions.
- Used `cd ./inhere` and `cat` to read the only human-readable file.

### Bandit Level 5 → Level 6
- Used `find` to locate a file with specific properties: human-readable, 1033 bytes in size, and in the `inhere` directory.

### Bandit Level 6 → Level 7
- Used `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null` to locate the password file.

### Bandit Level 7 → Level 8
- Used `grep "millionth" data.txt` to extract the password from a large text file.

### Bandit Level 8 → Level 9
- Used `sort data.txt | uniq -u` to find the only unique line in the file.

### Bandit Level 9 → Level 10
- Used `strings data.txt | grep "===="` to find the password among unreadable characters.

### Bandit Level 10 → Level 11
- Used `base64 -d data.txt` to decode the Base64-encoded password.

### Bandit Level 11 → Level 12
- Used `tr 'A-Za-z' 'N-ZA-Mn-za-m'` to decode the ROT13-encoded password.

### Bandit Level 12 → Level 13
- Created a temporary working directory using `mkdir /tmp/bandit12_temp`.
- Copied `data.txt` into the temporary directory.
- Used `xxd -r data.txt > data.bin` to convert the hexdump back to a binary file.
- Used `file` to check the type of `data.bin`.
- Repeatedly decompressed the file using `gzip`, `bzip2`, and `tar` until a readable text file was obtained.
- Used `cat` on the final file to retrieve the password.

### Bandit Level 13 → Level 14
- Found an SSH private key `sshkey.private` in the home directory.
- Used `ssh -i sshkey.private bandit14@localhost -p 2220` to log in as Bandit14.
- Read the password from `/etc/bandit_pass/bandit14` using `cat`.

### Bandit Level 14 → Level 15
- Used `nc localhost 30000` and entered the password to receive the next password.

### Bandit Level 15 → Level 16
- Used `openssl s_client -connect localhost:30001 -quiet` to establish an SSL connection and retrieved the password.

### Bandit Level 16 → Level 17
- Found an RSA private key in the home directory.
- Copied the key and saved it locally with proper permissions (`chmod 600`).
- Used `ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220` to log in as Bandit17.


## Notes:
- Used `find`, `grep`, `sort`, `uniq`, `strings`, `base64`, `tr`, `xxd`, `tar`, `gzip`, and `bzip2` commands to retrieve passwords.
- Used redirections like `2>/dev/null` to suppress errors.
- Practiced using pipes (`|`) for command chaining.
- Dealt with file extractions and decompressions systematically.
- Used `nc` and `openssl` for network-based challenges.
- Managed SSH keys and secure connections.
