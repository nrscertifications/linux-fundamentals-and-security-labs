# Security & Network Operations

This document summarizes Linux command-line exercises completed through the OverTheWire Bandit training environment. The focus of these exercises was character translation, encoded data handling, recursive decompression, SSH key permissions, and basic TCP/TLS service interaction.

## Character Translation & Data Obfuscation

### Objective

Decode obfuscated text using character translation utilities.

### Commands

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

### Operational Note

The `tr` utility translates or replaces characters from standard input. In this workflow, it is used to apply ROT13 character substitution, a basic text obfuscation method.

---

## Recursive Decompression Workflow

### Objective

Identify and extract nested compressed files until the readable source data is reached.

### Commands

```bash
mktemp -d
file data
xxd -r data > data.bin
gunzip data.bin
bunzip2 data
tar -xf data
file data
```

### Operational Note

This workflow demonstrates a structured approach to unknown file analysis:

* Create an isolated temporary workspace.
* Use `file` to identify the current file type.
* Use the correct extraction tool for the identified format.
* Repeat the process until readable content is reached.

This is useful when handling compressed files, archives, hex dumps, or unknown file formats in a controlled lab environment.

---

## SSH Key Permissions & Authentication

### Objective

Use SSH key-based authentication with proper private key permissions.

### Commands

```bash
chmod 600 sshkey.private
ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org
```

### Operational Note

SSH private keys require strict file permissions. The `chmod 600` command restricts the key so only the file owner can read and write it.

If a private key is too permissive, SSH may reject it for security reasons. This reinforces proper handling of authentication material and secure remote access workflows.

---

## Network Service Interaction with TCP

### Objective

Send data to a listening network service over a TCP connection.

### Commands

```bash
nc localhost 30000
```

### Operational Note

`nc`, also known as Netcat, can be used to open direct TCP connections to network services. It is useful for basic connectivity checks, service interaction, and troubleshooting simple client-server communication.

---

## Network Service Interaction with TLS

### Objective

Connect to a TLS-secured network service and send input through an encrypted session.

### Commands

```bash
openssl s_client -connect localhost:30001
```

### Operational Note

`openssl s_client` is used to test and interact with SSL/TLS-enabled services from the command line.

This workflow is useful for validating encrypted service connectivity, reviewing certificate details, and troubleshooting secure network communication in controlled environments.

## Security Note

This repository contains sanitized command syntax and conceptual workflows only. No passwords, private keys, challenge answers, or sensitive credentials are included.
