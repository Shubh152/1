Shubh\_Jain
---

`			#`Bandit\_level.1-level.15\_solutions
---

##0-1.
 to login in ssh server at <hostname> and <port> as <user>

~ssh <user>@<hostname> -p <port>~
---
##1-2.
 to work with dashed files use ‘<-’ instead of ’-’

~cat <-~
---

##2-3. 
to use <space>, use escape sequence \<space>

~cat spaces\ in\ this\ filename~
---
##3-4. to check hidden files in directory

~ls -a~
---
##4-5.  
check file type of all files , ascii files will be human readable .

~Cd inhere~

~File inhere/\*~  

File dir/\* prints  all file types in dir directory
---
##5-6. 
to find a file of size x bytes in y dir
(c for bytes)

~find y -size xc~   

here,

~find / -size 1033c~
---
##6-7.
~ find -user <username> -group <groupname> -size 33c~
---
##7-8.
 use grep to search within files

` `~grep -F <pattern> <filename>~

-F for fixed string pattern
---
##8-9. 
use diff by piping two stdout as stdin

~diff --normal <(sort -R data.txt | uniq --all-seperated -) <(sort -R data.txt | uniq -u -)~

can only use uniq -u with sorted files
---
##9-10.
 use grep to match output with at least == pattern after piping stdout from strings function ,strings will print all human readable characters

~strings data.txt | grep == -~
---
##10-11.
 decode the given base64 encoded data

~base64 -d data.txt~
---
.##11-12. 
use translate -t giving range as array set taking input from data.txt file , in default case it translates characters from set1 to set 2

~tr -t [A-Za-z] [N-ZA-Mn-za-m] < data.txt~
---
##12-13.
 first, retrieve the compressed file from hexdump file,

then decompress repeatedly using bzip2, gzip, tar

for reverse hexdump, ~xxd -r data\_copy.txt > data0.txt~

data0.txt is a compressed file of gzip, bzip2, tar which is checked by file command ,then rename file using mv to add appropriate suffix like gz, bz2

~gzip -d data0.txt.gz~

~bzip2 -d data0.txt.bz2~  
---
##13-14. 
since private key is already generated and given as file, to use private key for ssh server use -i tag

~ssh -i <filename> <user>@<hostname> -p <port>~
---
##14-15. 
path for password is given  in prev level, so we have to just transfer data between two ports on the localhost, using nc we check for the status of the ports 2220 (source) and 30000 (destination)

~nc -l localhost 2220   output: already in use~

~nc -l localhost 30000   output: already in use~

to send password string to port 30000 of localhost

(use <<<’’ for string and < for file )

~nc localhost 30000 <<< ‘<password for level14>’~
---