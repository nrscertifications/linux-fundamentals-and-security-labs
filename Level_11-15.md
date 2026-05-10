Level 11 -> 12
Command Used: 
    `strings data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`
Password found: `7x16...`

Level 12 -> 13
Commands Used: 
    `mktemp -d /tmp/nrs-dir.XXXXXX`
    `xxd -r data.txt > /tmp/nrs-dir.YTVwEN/DataBinary.txt`
    `ls -l /tmp/nrs-dir.YTVwEN`
    `cd /tmp/nrs-dir.YTVwEN/`
    `file DataBinary.txt`
    `mv DataBinary.txt DataBinary.gz`
    `gunzip DataBinary.gz`
    `file DataBinary`
    `mv DataBinary DataBinary.bz`
    `bunzip2 DataBinary.bz`
    `gunzip DataBinary.gz`
    `mv DataBinary DataBinary.tar`
    `tar -xf data5.bin`
    `file data6.bin`
    `bunzip2 data6.bin`
    `file data6.bin.out`
    `tar -xf data6.bin.out`
    `file data8.bin`
    `gunzip -c data8.bin > data9.bin`
    `file data9.bin`
    `cat data9.bin`
Password found: `FO5d...`

Level 13 -> 14
Command Used: ` `
Password found: ` `

Level 14 -> 15
Command Used: ` `
Password found: ` `
