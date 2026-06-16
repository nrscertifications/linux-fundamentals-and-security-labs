# File Searching & Data Processing

This document summarizes Linux command-line exercises completed through the OverTheWire Bandit training environment. The focus of these exercises was file searching, ownership filtering, text search, sorting, duplicate detection, readable string extraction, and Base64 decoding.

## Searching Files by Ownership and Size

### Objective

Locate a file based on owner, group, file type, and exact size.

### Commands

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /path/to/matching/file
```

### Operational Note

The `find` utility can search across the filesystem using multiple file attributes.

* `-type f` searches for regular files.
* `-user bandit7` filters by file owner.
* `-group bandit6` filters by group ownership.
* `-size 33c` matches files that are exactly 33 bytes.
* `2>/dev/null` suppresses permission-denied errors from standard error output.

This workflow is useful for file system audits, troubleshooting, and locating files when only partial metadata is known.

---

## Searching Text Within a File

### Objective

Find a specific line inside a text file using a keyword match.

### Commands

```bash
grep "millionth" data.txt
```

### Operational Note

The `grep` command searches text for matching patterns and returns the lines that contain those matches. It is commonly used for log review, configuration checks, and command-output filtering.

---

## Sorting and Identifying Unique Data

### Objective

Find a line that appears only once within a file containing repeated entries.

### Commands

```bash
sort data.txt | uniq -u
```

### Operational Note

Pipes allow multiple Linux commands to work together in a single workflow.

* `sort data.txt` organizes the file contents so duplicate lines are grouped together.
* `uniq -u` displays only lines that appear once.

This workflow is useful when reviewing logs, lists, exports, or repeated data where unique entries need to be identified.

---

## Extracting Readable Strings from a File

### Objective

Identify readable text embedded within a file and filter for a specific pattern.

### Commands

```bash
strings data.txt | grep -E "={2,}"
```

### Operational Note

The `strings` command extracts human-readable text from files that may contain non-readable or binary content.

The output is then filtered with `grep -E`, which enables extended regular expressions. The pattern `={2,}` searches for two or more equal signs in sequence.

This workflow is useful for inspecting unknown files, reviewing binary-like data, and extracting readable indicators without opening the file directly.

---

## Decoding Base64-Encoded Text

### Objective

Decode Base64-encoded content from the command line.

### Commands

```bash
base64 -d data.txt
```

### Operational Note

Base64 is an encoding format used to represent data as printable text. The `base64 -d` command decodes Base64 content back into readable output.

This workflow is useful when reviewing encoded configuration data, logs, tokens, or text-based encoded values in a controlled environment.
