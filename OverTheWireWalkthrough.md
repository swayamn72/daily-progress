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

## Current Level:


---

## Notes:
- Used `find`, `grep`, `sort`, `uniq`, `strings`, `base64`, and `cat` commands to retrieve passwords.
- Used redirections like `2>/dev/null` to suppress errors.
- Practiced using pipes (`|`) for command chaining.

---

