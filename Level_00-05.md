# Shell Navigation & File Handling

This document summarizes Linux command-line exercises completed through the OverTheWire Bandit training environment. The focus of these exercises was file system navigation, file identification, hidden files, special filename handling, and attribute-based file searches.

## Reading File Contents

### Objective

Read the contents of a text file from the command line.

### Commands

```bash
cat readme
```

### Key Concept

The `cat` command displays file contents directly in the terminal and is commonly used for quick file inspection and verification.

---

## Handling Special Filenames

### Objective

Access files containing shell-reserved characters that may be interpreted as command options.

### Commands

```bash
ls
cat ./-
```

### Key Concept

The filename `-` can be interpreted as a command option by the shell. Using `./` explicitly identifies the object as a file in the current directory.

---

## Working with Filenames Containing Spaces

### Objective

Access files that contain spaces and special characters in the filename.

### Commands

```bash
ls
cat "./--spaces in this filename--"
```

### Key Concept

Quotation marks preserve the filename exactly as written and prevent the shell from treating spaces as argument separators.

---

## Identifying Hidden Files

### Objective

Locate and access hidden files within a directory.

### Commands

```bash
cd inhere
ls -a
cat ./.hidden
```

### Key Concept

Files beginning with a period (`.`) are hidden from standard directory listings. The `-a` option displays all files, including hidden objects.

---

## Verifying File Types Before Reading

### Objective

Identify human-readable files before attempting to open them.

### Commands

```bash
cd inhere
file ./*
cat ./-file07
```

### Key Concept

The `file` utility determines the type of a file based on its contents rather than its name. This helps identify text files, binary files, archives, and other file formats before processing them.

---

## Searching for Files by Attributes

### Objective

Locate files based on size and permission characteristics.

### Commands

```bash
cd inhere
find . -type f -size 1033c ! -executable
cat ./maybehere07/.file2
```

### Key Concept

The `find` utility enables targeted searches using file attributes.

* `-type f` searches for regular files.
* `-size 1033c` matches files that are exactly 1033 bytes.
* `! -executable` excludes executable files.

This type of search is commonly used during troubleshooting, system administration, and file system audits.
