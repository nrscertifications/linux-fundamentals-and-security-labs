# OverTheWire Bandit: Levels 6-10

This file documents my work through Bandit levels focused on file searching, ownership, groups, text searching, sorting, filtering, printable strings, and Base64 decoding.

Passwords are intentionally not included.

---

## Level 6 -> 7

### Commands Used

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /path/to/matching/file
```

### What I Did

I used `find` to search the filesystem for a regular file owned by user `bandit7`, owned by group `bandit6`, and exactly 33 bytes in size. I redirected permission errors to `/dev/null` so the useful result was easier to see.

### Concept Practiced

This level reinforced advanced file searching with `find`, including searching by owner, group, file size, and suppressing permission-denied errors.

### Notes

Password not included. Replace `/path/to/matching/file` with the matching path found from the `find` command.

---

## Level 7 -> 8

### Commands Used

```bash
grep "millionth" data.txt
```

### What I Did

I used `grep` to search inside `data.txt` for the line containing the word `millionth`.

### Concept Practiced

This level reinforced searching text inside a file using `grep`.

### Notes

Password not included.

---

## Level 8 -> 9

### Commands Used

```bash
sort data.txt | uniq -u
```

### What I Did

I sorted the contents of `data.txt` and used `uniq -u` to display the line that appeared only once.

### Concept Practiced

This level reinforced using pipes to combine commands. It also practiced sorting data before using `uniq`, since `uniq` works best when duplicate lines are grouped together.

### Notes

Password not included.

---

## Level 9 -> 10

### Commands Used

```bash
strings data.txt | grep -E "={2,}"
```

### What I Did

I used `strings` to extract readable text from the file and piped the output into `grep` to search for lines containing repeated equal signs.

### Concept Practiced

This level reinforced extracting human-readable text from a file and filtering command output using regular expressions.

### Notes

Password not included.

---

## Level 10 -> 11

### Commands Used

```bash
base64 -d data.txt
```

### What I Did

I used `base64 -d` to decode the Base64-encoded contents of `data.txt`.

### Concept Practiced

This level reinforced recognizing and decoding Base64-encoded text from the Linux command line.

### Notes

Password not included.
