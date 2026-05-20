## Level 16 -> 17

### Commands Used

```bash
nmap -p 31000-32000 bandit.labs.overthewire.org
nmap -sV -p 31000-32000 bandit.labs.overthewire.org
openssl s_client -connect localhost:31790 -quiet
mkdir -p ~/.ssh/sshkeys && touch ~/.ssh/sshkeys/sshkey.16
nano ~/.ssh/sshkeys/sshkey.16
chmod 600 ~/.ssh/sshkeys/sshkey.16
ssh -i ~/.ssh/sshkeys/sshkey.16 bandit17@bandit.labs.overthewire.org -p 2220
```

### What I Did

I scanned the required port range from `31000` to `32000` using `nmap` to identify open TCP ports on the Bandit server. After finding multiple open ports, I used `nmap -sV` to check the service versions and identify which services were using SSL/TLS.

The service scan showed that port `31790` was running an SSL-enabled service that prompted for the current Bandit password. I connected to that port using `openssl s_client`, entered the current password, and received an RSA private key for the next level.

After receiving the key, I saved it locally inside my SSH key directory, restricted the file permissions with `chmod 600`, and used the key with `ssh -i` to log in as `bandit17`.

### Concept Practiced

This level reinforced network port scanning, service version detection, SSL/TLS connections, and SSH private key authentication. It also practiced identifying the correct service from multiple open ports and securing private key files so OpenSSH would accept them.

### Notes

Port `31518` also used SSL, but it was only an `ssl/echo` service. Port `31790` was the correct port because it responded with the password validation prompt.

The RSA private key should be saved locally so it can be reused later. Private key files should use restrictive permissions such as `chmod 600`, because OpenSSH rejects private keys that are too open.

Passwords and private key contents are not included in this repository.
