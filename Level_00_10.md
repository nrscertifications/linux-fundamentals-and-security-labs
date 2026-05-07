# Level 0 -> 1
Command used: `cat readme`
Password found: `ZjLj...`

# Level 1 -> 2
Command used: `cat ./-`
Password found: `263J...`

# Level 2 -> 3
Command used: `cat ./"--spaces in this filename--"`
Password found: 'MNk8...'

# Level 3 -> 4
Command used: `cd inhere' 'ls -a` , `cat ./"...Hiding-From-You`
Password found: `2Wmr...`

# Level 4 -> 5
Command used: `file ./*` , `cat ./-file07`
Password found: `4oQY...`

# Level 5 -> 6
Command used: `find . -type f -size 1033c ! -exec` , `cat ./maybehere07/.file2`
Password found: `HWas...`

# Level 6 -> 7
Command used: `find / -name "*.*" -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null`
Password: `morb...`

# Level 7 -> 8
Command used: `grep "millionth" data.txt`
Password: `dfwv...`

# Level 8 -> 9 
Command used: `sort data.txt | uniq -u`
Password: `4CKM...`

# Level 9 -> 10
Command used: `strings data.txt | grep -E "={2,}"`
Password: `FGUW...`

# Level 10 -> 11
Command used: `base64 -d data.txt`
Password: `dtR1...`
