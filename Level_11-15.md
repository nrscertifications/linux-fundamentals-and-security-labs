# OverTheWire Bandit: Levels 11-15

This file documents my work through Bandit levels focused on ROT13 decoding, hex dump reversal, compressed files, archive extraction, SSH private key usage, and basic network communication with `nc`.

Passwords and private key contents are intentionally not included.

---

## Level 11 -> 12

### Commands Used

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

### What I Did

I used `cat` to display the contents of `data.txt` and piped the output into `tr` to decode the ROT13 text.

### Concept Practiced

This level reinforced using `tr` for character translation and recognizing ROT13 as a simple letter substitution method.

### Notes

Password not included.

---

## Level 12 -> 13

### Commands Used

```bash
temp_dir=$(mktemp -d)
cp data.txt "$temp_dir"
cd "$temp_dir"

xxd -r data.txt data
file data

mv data data.gz
gunzip data.gz
file data

mv data data.bz2
bunzip2 data.bz2
file data

mv data data.gz
gunzip data.gz
file data

mv data data.tar
tar -xf data.tar
file data5.bin

tar -xf data5.bin
file data6.bin

mv data6.bin data6.bz2
bunzip2 data6.bz2
file data6

mv data6 data6.tar
tar -xf data6.tar
file data7.bin

mv data7.bin data7.gz
gunzip data7.gz
file data8

cat data8
```

### What I Did

I created a temporary working directory, copied the data file into it, and reversed the hex dump using `xxd -r`. I then used `file` repeatedly to identify each file type and extracted or decompressed each layer until the final readable file was reached.

### Concept Practiced

This level reinforced a practical troubleshooting workflow: identify the file type, rename the file with the correct extension when helpful, extract or decompress it, and repeat until the final readable text is found.

### Notes

Password not included. Temporary directory names can be different each time.

---

## Level 13 -> 14

### Commands Used

```bash
ls
file sshkey.private
chmod 600 sshkey.private
ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org
```

### What I Did

I identified the SSH private key file, restricted its permissions with `chmod 600`, and used it with `ssh -i` to log in as the next user.

### Concept Practiced

This level reinforced SSH private key authentication and proper private key file permissions. SSH private keys should not be publicly exposed or left with overly open permissions.

### Notes

Private key contents and passwords are not included.

---

## Level 14 -> 15

currently in progress...
