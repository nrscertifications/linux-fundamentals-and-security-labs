# OverTheWire Bandit: Levels 0-5

This file documents my work through the first Bandit levels, focusing on basic Linux command-line navigation, reading files, handling special filenames, hidden files, file types, and file searching.

Passwords are intentionally not included.

---

## Level 0 -> 1

### Commands Used

```bash
cat readme
```

### What I Did

I used `cat readme` to display the contents of the `readme` file and retrieve the password for the next level.

### Concept Practiced

This level reinforced basic Linux file reading using the `cat` command.

### Notes

Password not included.

---

## Level 1 -> 2

### Commands Used

```bash
ls
cat ./-
```

### What I Did

I used `ls` to list the files in the current directory. The file was named `-`, so I used `cat ./-` to read it safely.

### Concept Practiced

This level reinforced how to work with special filenames in Linux. Using `./-` tells the shell to treat `-` as a file in the current directory instead of interpreting it as a command option.

### Notes

Password not included.

---

## Level 2 -> 3

### Commands Used

```bash
ls
cat "./--spaces in this filename--"
```

### What I Did

I used `ls` to view the file in the current directory. Because the filename contained spaces and special characters, I wrapped the filename in quotes and used `cat` to read it.

### Concept Practiced

This level reinforced how to handle filenames that contain spaces or special characters by using quotation marks.

### Notes

Password not included.

---

## Level 3 -> 4

### Commands Used

```bash
ls
cd inhere
ls -a
cat ./.hidden
```

### What I Did

I listed the files in the current directory, moved into the `inhere` directory, and used `ls -a` to show hidden files. I then used `cat` to read the hidden file.

### Concept Practiced

This level reinforced Linux hidden files and directory navigation. Files that begin with a dot are hidden from normal `ls` output and require `ls -a` to display.

### Notes

Password not included.

---

## Level 4 -> 5

### Commands Used

```bash
cd inhere
ls
file ./*
cat ./-file07
```

### What I Did

I moved into the `inhere` directory and used `file ./*` to check the file types of each file. After identifying the human-readable file, I used `cat` to read it.

### Concept Practiced

This level reinforced the use of the `file` command to identify file types before opening them. It also continued practice with special filenames that begin with `-`.

### Notes

Password not included.

---

## Level 5 -> 6

### Commands Used

```bash
cd inhere
find . -type f -size 1033c ! -executable
cat ./maybehere07/.file2
```

### What I Did

I moved into the `inhere` directory and used `find` to search for a regular file that was exactly 1033 bytes and not executable. After identifying the matching file, I used `cat` to read it.

### Concept Practiced

This level reinforced searching for files by size and permissions using the `find` command.

### Notes

Password not included.
