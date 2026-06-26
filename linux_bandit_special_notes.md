## Intro

**This note contains things to know when solving the OverTheWire Bandit series of challenges.**


_OverTheWire Link: [Bandit-Challenges](https://overthewire.org/wargames/bandit/)_

**Topics covered**
- Linux Commands (Mostly)
- Bash Script Writings
- Git Commands

## GET START
- Windows -> Powershell
- Linux -> Terminal 
- Mac -> Terminal


## References

- [bandit0](#bandit0)
- [bandit1](#bandit1)
- [bandit2](#bandit2)
- [bandit3](#bandit3)

### Bandit0
- [Go Back to Reference](#references)
```
ssh user_name@server_IP -p 2220
```
- `ssh` starts a secure remote shell connection.
- `-p` specifies the port number.
- `user_name@server_IP` specifies username and remote server. 
#### Examples: `ssh bandit0@bandit.labs.overthewire.org -p 2220`.


```
ls 
```
- `ls` list the files and folders in the current directory.
#### Examples: `ls`.


```
cat 'file_name'
```
- `cat` displays the content of the specified 'file_name'.
#### Examples: `cat readme`.


##
<!-- 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR -->


### Bandit1
- [Go Back to Reference](#references)

```
ssh user_name@server_IP -p 2220
```
- `ssh` starts a secure remote shell connection.
- `-p` specifies the port number.
- `user_name@server_IP` specifies username and remote server. 
#### Examples: `ssh bandit1@bandit.labs.overthewire.org -p 2220`.


```
ls 
```
- `ls` list the files and folders in the current directory.
#### Examples: `ls`.


```
cat ./'file_name'
```
- `./` option tells the `cat` command to open file included `-` in its name instead of interpreting `-` as a standard input.
#### Examples: `cat ./-`.


##
<!-- PK8fYLZg2hnHSz83plBL1iEPKdD3QToB -->


### Bandit2
- [Go Back to Reference](#references)

```
ssh user_name@server_IP -p 2220
```
- `ssh` starts a secure remote shell connection.
- `-p` specifies the port number.
- `user_name@server_IP` specifies username and remote server. 
#### Examples: `ssh bandit2@bandit.labs.overthewire.org -p 2220`.


```
ls 
```
- `ls` list the files and folders in the current directory.
#### Examples: `ls`.


```
cat ./'file\ name\ with\ spaces'
```
- `./` display files with dashes in their names.
- `\` specifies spaces in the file_name.
#### Examples `cat ./--spaces\ in\ this\ filename--`.


##
<!-- 7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME -->


### Bandit3
- [Go Back to Reference](#references)

```
ssh user_name@server_IP -p 2220
```
- `ssh` starts a secure remote shell connection.
- `-p` specifies the port number.
- `user_name@server_IP` specifies username and remote server. 
#### Examples: `ssh bandit3@bandit.labs.overthewire.org -p 2220`.


```
ls 
```
- `ls` list the files and folders in the current directory.
#### Examples: `ls`.


```
cd 'directory_name'
```
- `cd` changes the current working directory to the specified directory. 
#### Examples `cd inhere`.


```
cat .`file_name`
```
- `.` is actually a part of the filename and filename with a dot in the front is hidden from the bash.
#### Examples: `cat ...Hiding-From-You`.


##
<!-- xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq -->


### Bandit4
- [Go Back to Reference](#references)




level4 input:
ls -l
cd "directory_name"
ls -l
file ./"file_name"
cat "file_name" for ASCII text
//"file" + "file_name" determines that file type.
level4 output:4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

level5 input: 
ls -a
du -h */.*
ls -l *
ls -l */.*
"ls -a -l */.*" to locate the 1033 bytes file
// ls -a is used to display the hidden files, du -h */.* is to display size of all hidden files(.*) in all directories = "*/.*", ls -l displays the properties, creator/user, date created, name, ls -l */.* display all info of hidden files inside all directories.
level5 output:HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

level6 input:
Verify:
ls -l */.* | grep "bandit", 
ls -l bandit6/.* bandit7/.* | grep "bandit",
find -user bandit7,
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
//"find /" search start from root directory for user bandit7 group bandit6 siez for 33bytes
//2>/dev/null filter out results permission denied.
level6 output:morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

level7 input:
cat data.txt | grep "millionth"
//
level7 output:dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

level8 input:
sort "file",
sort "file" | uniq -c,
//sort by default gives text in order and in pairs,
//uniq can't by default, by -c list and count repeated line and duplicate one.
level8 output:4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

level9 input:
strings -a data.txt
//filter by default gives human-readable text.
level output:FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

level10 input:
base64 -d data.txt
//decode base64 encoded data
level10 output: The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

level11 input:
tr 'A-Za-z' 'N-ZA-Mn-za-m' <<< "Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4"
//before <<< is ROT 13 encoding method
level11 output:7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

level12 input:
mktemp -d "file",
cd /tmp/tmp.Zva9APOSNm,
cd /tmp/tmp.ZjeXU6pBkx,
cp "file" "file_name",
xxd -r "file" >> "save_file"
//">>" saves output to a file
mv "file" "file.gz"
//rename to gz compression
gzip -d "file.gz"
decompress gz file
file "file"
//identify file type
mv "file" "file.bz2"
//rename file to bz compression
bzip2 "file.bz2"
//decompress bz2 file
mv "file" "file.tar"
rename file to tar compression
tar -xvf "file.tar"
//decompress tar file
level12 output:The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

level13 input:
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
//copy file on port 2220 from user bandit13 of server ... file name sshkey.private to hidden layer for destination
ssh -i '/path/to/keyfile' username@server
cat /etc/bandit_pass/bandit14
level13 output: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

level14 input: 
echo "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS" | nc localhost 30000
//echo/send "level13password"/"text" |/and nc/send to localhost/computer 30000/on port 30000
level14 output: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

level15 input: 
openssl s_client localhost:30001
//openssl s_client gives secure connection to localhost on port 30001
"level14password"
level15 ouput:kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

level16 input:
nmap -sV -p "port"or"port-range" localhost
//sV gives listening port and echo port.
//31790/tcp open  ssl/unknown
//31518/tcp open  ssl/echo
openssl s_cliet -connect localhost:31790 -quiet
//"-quiet" Extends the content from KEYUPDATE phrase
//-----BEGIN RSA PRIVATE KEY-----vWkU
-----END RSA PRIVATE KEY-----
scp -P "port number"user@server:source destination
ssh -i '/path/to/keyfile' username@server
cat /etc/bandit_pass/bandit17
level16 output:EReVavePLFHtFlFsjn3hyzMlvSuSAcRD

level17 input:diff "file1" "file"
// differentiate two files 
level17 output:x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

level18 input:
scp -P 2220 bandit18@bandit.labs.overthewire.org:readme .
//scp -P "port number"user@server:source destination
cat readme
level18 output:cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8

level19 input: 
stat bandit20-do
//setuid(set user id) is a special permission in Unix-like operating system  that allows an executable file to run with the privileges of its owner
./bandit20-do
//"./" executes file
./bandit20-do cat /etc/bandit_pass/bandit20
// ./setuid "commands"
//give privileges as bandit20
level19 output:0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

level20 input:
echo "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO" | nc -l localhost 40000
// "nc -l" host as server to listen to messages and to response 
// write "passwd" down | as a host on port 40000
./suconnect 40000
level20 output:EeoULMCra2q0dSkYj561DX7s1CpBuOBt

level21 input:
cd /etc/cron.d
cat *
cat cd /usr/bin/cronjob_bandit22.sh
//
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
//
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
level21 output:tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

level22 input:
mktemp -d
cp "cronjob" "tmpFile"
//cronjob starts $/bin/bash
nano temFile
//Ctrl + X(Exit);Ctrl+O(Write Out)
//[number] + stopped = Ctrl + Z
vim file.sh
//:q(exit and save)
//:q!(exit without save)
level22 output:0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

level23 input:
//Take a close reading to the goal!!!
mktemp -d 
nano "file.sh" : 
//#! /bin/bash
//cat /etc/bandit_pass/bandit24 > /"tmp file path"/password
chmod "permission number" "file.sh"
chmod "permission number" "password"
//password is an empty file
//rwx(read, write, execute) are 4,2,1.
//permission number is three numbers combined of permissions to User, Group, Others
//Each number is the sum of levels of permission rwx you are giving.
//chmod -rwxr-xr-x means chmod 755
//because r-x is sum of 4 and 1
cp "file.sh" /var/spool/bandit24/foo/
cat password
//chmod 777 "tmpFolder" is a step also
//chmod folder chmod that permission to all files inside that folder
level23 output:gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

level24 input:
#!/bin/bash
for i in {0000..9999}
do
        echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i >> poss.txt
done
cat poss.txt | nc localhost 30002 > result.txt
"""
The entire thing in line 4 is write into poss.txt.?
cat poss.txt will not input everything at once.?
"""
for i in {0000..9999}; do echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i ;done | nc localhost 30002
//head -n "number"
//cat the first "number" line
//grep -v "text"
//"grep -v" differ "text" from input text
level24 output:iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

level25 input:
cat /etc/passwd | grep 26
///etc/passwd is often config zone
"""
#!/bin/sh

export TERM=linux
//The above emulates Linux environment
exec more ~/text.txt
//When shell, process of login would be take over to display text.txt
exit 0
//then exit out
"""
//OR
:set shell=/bin/bash
:shell
level25 output:s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ

level26 input:
./bandit27-do cat /etc/bandit_pass/bandit27
level26 output:upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB

level27 input:
git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo
//host:port 
cd repo
cat readme
level27 output:The password to the next level is: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN

level28 input: 
cd repo
git log
//gives the history version of files
git show *
//gives the previous version of the files
level28 output:4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7

level29 input:
git branch -a
//"branch -a" gives all remotes or local respository
git checkout "branchName"
cat *
//Search everything available on the screen!
level29 output:qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL

level30 input:
git tag
//Create, list, delete or verify a tag object signed with GPG
//GPG: privacy guard
git show secret	
//
level30 output:fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy

level31 input:
ls lah 
cat .gitignore
rm .gitignore
echo "May I come in?" > key.txt
git commit -am "updateComment"
git push 
level31 output:3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K

level32 input:
$0
//return from shell
cat /etc/bandit_pass/bandit33
level32 output:tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0

===========12425
