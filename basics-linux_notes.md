# Intro
- This note was created to better navigate in Linux, and accomplish overTheWire CTF challenges.

## Reference

- [List of Commands](#list-of-commands)
- [Permission Distribution](#permission-distribution)
- [SQL Database Query](#sql-database-query)
- [Filter Operation Usage](#filter-operation-usage)
- [SQL Join Usage](#sql-join-usage)
- [More](#more)
- [Encryption Specials](#encryption-specials)
    - [Caesar Cipher](#caesar-cipher)
    - [Openssl Cipher](#openssl-cipher)
    - [Hash Cipher](#hash-cipher)
- [Network Protocol Analyzer](#network-protocol-analyzer)
- [IDS/IPS Suricata](#idsips-suricata)
- [GOOD TO EXPLORE](#good-to-explore)

<!-- List pf Commands -->

## List of commands: 
[GO BACK](#intro)

`whatis "command“`
- Description: Outputs description about the "command"

`man "command"`
- Shows mannual infomation about "command"

`apropos -a "key phrases"`

- Searches through mannual information for "key phrases"

`pwd`
- Current path

`ls`
- List files
- "-a" list hidden files.
- "-l" list permissions of files.

`clear`
- Clear the terminal

`find "path"+"possible_dir_name"`
- Searches "possible_dir_name" in "path"

`find "path"+"possible_dir_name" -name "possible_file_name"`
- Searches "possible_file_name".(This file name MUST be inputed inside "")
- "*" on either OR both sides of the possible_file_name indicates unknown characters
- Ex: find "path"+"possible_dir_name" -name "*team*"
- This Ex searches for files name with "team" in the middle.
- find "path"+"dir_name" -mtime "number_of_days"
- Searches for all files in directory that is modified within the "number_of_day"
- "-tmin" searches for modifications done within how many minutes.

`cp "file" "copyFileName"`
- Creates a copy of "file" with "copyFileName"

`mv "file" "newDirectoryPath"`
- Move "file" to a new location
- If "newDirectoryPath" is one dir before the current dir, uses ../"path"
- OR mv "file" "newFileName" - renames "file"

`cd "directory"`
- Change the current working directory.

`cd ../`
- Connect one directory before current directory

`rm "file"`
- Delete "file"

`rm -r "file"`
- Remove "file" with recursive

`touch "path"/"file"`
- Creates an empty file (if it doesn't exist) or updates its timestamp.

`mkdir`
- Create directory

`rmdir "name"`
- Remove directory by name

`echo "message" -  "file"`
- Print/write "message" into "file"
- ">" does overwrite, ">>" does append

`echo "hell world"  >> "file"`
- ">>" does append the content

`cat "file" > "file2"`
- Read/write "file" content into "file2"

`echo "content ${another command}"`
- ${} is parameter expansion.

`expr "calculation"`
- Expression allows calculation
- Notice that all elements should separated by spaces.
- Example: expr 1 + 1 NOT expr 1+1

`sudo apt install "software name"`
- Install a software

`sudo apt remove "software name"`
- Uninstall a software

`apt list --installed`
- List the installed softwares

`head`
- Displays just the beginning of a file, by default 10 lines.
- Change the lines of display: -n "number of lines"
- Exmaple: head -n 10 "file anme"

`tail`
- Displays the ending of a file, by default 10 line.

`less`
- Returns the content of a file one page at a time.

`grep "phraseToSearch" "fileToSearch"`
- Searches input phrases in input files
- If "phraseToSearch" contain spaces, use "", else without "" is fine.

`|`
- Piping "|" passes last command outputs as inputs for the next command
- Examples: ls /home/analyst/reports | grep OS

`nano "fileName"`
- Edits file content with tool nano
- Ctrl + O - Save; Ctrl + X - Exit


## PERMISSION DISTRIBUTION
[GO BACK](#intro)

`chmod "user/group/other""-/+""r/w/x" "file_name"`

- "chmod" distributes permissions.
- "user/group/other" are simplified as "u/g/o"
- "r/w/x" written as "read/write/exexcute"
- "-/+" plus/adds permissons, minus/removes permissions.
- "," separate permission for different u/g/o
- Ex: chmod u-w,g-w "file_name" removes wrtie permission for both user and group.

`chmod "###" "file_name"`

- "###" 3 unique numbers can represent the permissions
- 4 = read, 2 = write, and 1 = execute
- EX: chmod 440 "file_name" means permission to read for user and group only.

`sudo useradd "user_name"`

- "-g" sets user's default group;
- Adds new user to the system

`sudo userdel "user_name"`

- Deletes a existed user from the system
- "-r" deletes all files in user's home directory
- Ex: sudo userdel -r "user_name"

`usermod`

- Modifies existing users with options "-g" and "-G".
- Modifies the existing to existing group with "-a".
- "-d" changes the home directory of the user.
- Ex: sudo usermod -d "path"
- "-l" changes the user's login name.
- "-L" locks the account

`chown`

- Change the ownership of the files OR directory
- Ex: sudo chown "user_name" "file_name"
- Changes the ownership of the "file_name" to "user_name"
- Ex: sudo chown :"group_name" "file_name"
- Changes the ownership of the "file_name" to "group_name".
- Note!!! ":" must be added before "group_name" to indicates it's a group.
- "-G -a" adds the user to additional groups

`cat /etc/passwd`

- Outputs the existing users in the system
- "/etc/group" output the existing groups

`id -nG "user_name"`

- Shows supplementary group

`groupdel "group_name"`

- Deletes group that is named "group_name".
- Identical group was created as a new user was created.


## SQL DATABASE QUERY
[GO BACK](#intro)

`SELECT "column_name" FROM "table_name";`

- Outputs "column_name" data from "table_name".
- Each sql command ends with ";".
- Use "," comma to separate tow or more column_name.

`SELECT "column_name" FROM "table_name" ORDER BY "column_name";`

- "ORDER BY" sets which column to references.
- Ex: SELECT "column_name" FROM "table_name" ORDER BY CustomerId;
- Outputs "column_name" data from the smallest to greatest id number.
- The default of "ORDER BY" is smallest to greatest for numbers,
- The first letter in alphabeta to the last letter.
- Add "DESC" to the end of "column_name" to specify the opposite/descending order.

`sudo mysql "database_name"`

- Conectes the database named "database_name".

`SELECT "column_name" FROM "table_name" WHERE "column_name" = "search_phrase";`

- Outputs "column_name" data from "table_name" that matches "search_phrase"
- Ex: `SELECT job_position FROM "table_name" WHERE job_position = "IT_Staff";
- Outputs data about IT_Staff from "table_name".

`SELECT "column_name" FROM "table_name" WHERE "column_name" LIKE "possible_phrase";`

- Searches for "possible_phrase" at "column_name" from "table_name".
- "%" percentage sign substitutes for any number of other characters.
- Ex: ...LIKE "possible_phrase%" searches data that starts with "possible_phrase".
- Ex: ...LIKE "%possible_phrase" searches data that ends with "possible_phrase".
- "_" underscore symbol only substitutes for one other character.
- Ex: ...LIKE "possible_phrase_" searches data that starts with "possible_phrase" follow by ONLY one character.
- Ex: ...LIKE "_possible_phrase_" searches data that starts with ONLY one character, "possible_phrase" in the middle, follows by ONLY one character.


## FILTER OPERATION USAGE
[GO BACK](#intro)

`SELECT "column_name" FROM "table_name" WHERE "column_name" "operator_sign" "compare_value";`

- This searches for vaule of "column_name" that is "operator_sign" in comparsion to "compare_value"
- Notice: "<> " indicates not equal to sign.

`SELECT "column_name" FROM "table_name" WHERE "column_name" BETWEEN "start_value" AND "end_value";`

- Searches for range of values that are between the "start_value" and "end_value".

`SELECT "column_name" FROM "table_name" WHERE "column_name" = "1specific_value" OR "2specific_value";`

- Searches and returns column data where "column_name" has either "1specific_value" or "2specific_value";
- WHERE NOT "column_name" = "specific_value"; returns data column that are not "specific_value".
- Ex: >> SELECT "column_name" FROM "table_name" WHERE "job_position" NOT = 'finance'
- This searches and returns job_position columns that are not finance.


## SQL JOIN USAGE
[GO BACK](#intro)

```
SELECT "column_name"
FROM "table1_name" INNER JOIN "table2_name" 
ON 'table1_name'+".'column_name'" = 'table2_name'+."'column_name'";
```
- You MIGHT have all those lines in a single line when entering.
- You must specify the two tables to join by including the first or left table after FROM and the second or right table after INNER JOIN.


```
SELECT "column_name"
FROM "table1_name" LEFT JOIN "table2_name" 
ON 'table1_name'+".'column_name'" = 'table2_name'+."'column_name'";
```
- LEFT JOIN returns all the records of the first table, but only returns rows of the second table that match on a specified column. 
- You MIGHT think "=" as "and".


```
SELECT "column_name"
FROM "table1_name" Right JOIN "table2_name" 
ON 'table1_name'+".'column_name'" = 'table2_name'+."'column_name'";
```
- RIGHT JOIN returns all of the records of the second table, but only returns rows from the first table that match on a specified column. 
- if you're checking for is a column value is null, use where 'column_name' is null;


```
SELECT "column_name"
FROM "table1_name" Right JOIN "table2_name" 
ON 'table1_name'+".'column_name'" = 'table2_name'+."'column_name'";
```
- FULL OUTER JOIN query include all records from both tables. Similar to INNER JOIN, the order of tables does not change the results of the query. 

## MORE
[GO BACK](#intro)

`SELECT AVG("numerical_data")`
- Returns a single number that represents the average of the numerical data in a column;

`SELECT COUNT("numerical_data")`
- Returns a single number that represents the number of records returned from a query;

`SELECT SUM("numerical_data")`
- Returns a single number that represents the sum of the numerical data in a column;

## Encryption Specials


## Caesar Cipher
[GO BACK](#intro)

```
tr "order_of_alphabeta" "expected_order_of_alphabeta"
```
- Translates the "order_of_alphabeta" to the "expected_order_of_alphabeta"

### Examples

**_Encrytion_**

__INPUT:__
`echo 'Hello World' | tr "a-zA-Z" "b-zaB-ZA"`
-  Print(`echo`) "Hello World" by translating(`tr`) it from the order of (`a-zA-Z`) becomes (`b-zaB-ZA`).
- In other word, **if the original spot for letter A has the content of A, now its content became B**, because the first letter of expected alphabeta is B, and the **last letter of the expected alphabeta is A because it's from B to Z then A (B-ZA)**.

__OUTPUT:__
`Ifmmp Xpsme`
- Every letter in `Hello World` moves 1 place forward outputs `Ifmmp Xpsme`.

**_Decrytion_**


__INPUT:__
`echo 'Ifmmp Xpsme' | tr  "b-zaB-ZA" "a-zA-Z"`
-  Print(`echo`) "Ifmmp Xpsme" by translating(`tr`) it from the order of (`b-zaB-ZA`) to (`a-zA-Z`).
- In other word, **if the original spot for letter A has the content of B, now its content became A**, because the first letter of expected alphabeta is A, and the **last letter of the expected alphabeta is Z because it's from A-Z (A-Z) now**.

__OUTPUT:__
`Hello World`
- Every letter in `Ifmmp Xpsme` moves 1 place backward outputs `Hello World`.


## Openssl Cipher
[GO BACK](#intro)

### aes-256-cbc Cipher: 
```
echo 'phrase_to_encrypt' | openssl aes-256-cbc -a -k 'secret_phrase'
```
- `-a` option translates binary data into plaintext by applying base64 encoding on encrypted binary data.
- `-d` option is used to decrypt.
- `-A` option puts all output in a line.
- `-pbkdf2` iterates and repeats the password-derivation calculation **10,000** times before producing the AES key.
- `iter 'iteration_times'` repeats the calculation 'iteration_times' times.
- `-k 'secret_phrase'` sets a symmetric secret for both encryption and decryption.
- `in 'input_file'` must used together with `out 'file_name'`; Sets input text file.
- `out 'file_name'` sets file to store the output text.

### Examples
**_aes-256-cbc Encryption_**

__INPUT:__
```
echo 'Hello World' | openssl aes-256-cbc -a -k 'abc123'
```
- encrypt `Hello World` using aes-256-cbc with secret `abc123`;

__OUTPUT:__
`U2FsdGVkX1+BvPUluKzWUKVvLPJC5f+Ub4L2Gz9i2eA=`
- The output will be **different each time as a random salt value was generated** each time.


<!-- **_aes-256-cbc Decryption_** -->

\
**_aes-256-cbc Decryption_**

__INPUT:__
```
echo 'U2FsdGVkX1+BvPUluKzWUKVvLPJC5f+Ub4L2Gz9i2eA=' | openssl aes-256-cbc -a -d -k 'abc123'
```
- `-d` option is used to decrypt.
- *All other options MUST be the same during encryption and decryption*

__OUTPUT:__
`Hello World`


## HASH CIPHER
[GO BACK](#intro)

```
sha256sum 'file_name/content'
```
- Computes the SHA-256 hash (digest) of a `file_name` or standard input.

`cmp`
- compare the two files byte by byte. If a difference is found, the command reports the byte and line number where the first difference is found.


## Network Protocol Analyzer
[GO BACK](#intro)

`sudo tcpdump [-i interface] [option(s)] [expression(s)]`
-  `option(s)` are optional and provide you with the ability to alter the execution of the command.
- `-D` outputs a list of interfaces as reference.
- `-i` specifies interface(s) to capture
- `-w [filename]` specifies a specific file to save.
- `-r [filename]` specifies a specific file to open.
- `-v` or `-vv` or `-vvv` specifies the verbosity of the information.
- `-c [number of packet]` specifies the number of packets to capture.
- `-n` disables hostname resolutions for IP Addresses.
- `-nn` disables resolution for both hostname and port.
- `&` tells the terminal to run the command in the background.
- `expression(s)` are a way to further filter network traffic packets so that you can isolate network traffic. 
- `and`, `or`, `not` specifies boolean operators.

`curl [url]`
- `curl` sends HTTP, HTTPS, FTP, and other protocol requests to a URL or IP address.


## IDS/IPS Suricata
[GO BACK](#intro)

A Rule Structure of an IDS/IPS has:

Action
- alert
- drop(IPS only!)
- pass
- reject


Header 
- `[protocol] [traffic_source][source_port] -> [traffic_destination][destination_port]`


Rule_Options
- `msg: [alert_text]` : specifies text message to print when alert(s) happen.
- `flow: [state], [direction]` specifies network packets with specific state AND direction to filter.
- `content: [http_method]` : specifies a http method to look for.
- `sid: [unique_numerical_value]` : specifies a numerical value for the signature rule.
- `rev: [numerical_value]` : indicates the current signature version. 

Command(s):

`sudo suricata -r [input_filename] -S [custom_rules_filename] -k none` 
- `-r [input_filename]` specifies input files to process.
- `-S [custom_rules_filename]` specifies rule file to use for the filter.
- `-k none` instructs Suricata disable all checksum checks.(not warn about checksum errors)

`jp . [JSON_file_path]`
- `jp` instructs a command-line tool for processing JSON payload.
- `.` instucts jp to take in all data from the [JSON_file_path].
More `jq` Options:
- `-c [selected_fields]` compact output into selected field(s)/object(s) only.
>Example(s): `jq -c ".timestamp" filename`. \
>If a specific object is inside a field: use `.[field][object]`.

`jp "select([field/object(s)==[value]])" [file_path]`
- `select(...)` is a jq function instucts a filter for a specific condition.
- `[field/object(s)==[value]]` specifies a specific condition to filter.
>Example: `jp "select(.flow_id == 1001)" file.json` 
> - filters for data that has flow_id field equals 1001 from file.json.

## Good To Explore
[GO BACK](#intro)

- `history` : View previously executed commands.
- `whoami` : Display the username of the current user.
- `uname -a` : Display detailed system information, including the kernel version and architecture.
- `hostname` : Display the system's hostname.
- `file "file_name"` : Determine the type of a file based on its contents.
- `stat "file_name"` : Display detailed information about a file, such as permissions, size, and timestamps.
- `wc "file_name"` : Count the number of lines, words, and bytes in a file.
    - `-l` counts lines only.
    - `-w` counts words only.
    - `-c` counts bytes only.
- `sort "file_name"` : Sort the lines of a file alphabetically or numerically.
- `uniq "file_name"` : Remove or display consecutive duplicate lines.
    - Often used together with `sort`.
- `cut -d "delimiter" -f "field_number" "file_name"` : Extract specific columns or fields from each line of a file.
- `awk '{print $1}' "file_name"` : Process and manipulate text by columns or fields.
- `sed 's/old_text/new_text/' "file_name"` : Search for and replace text in a stream or file.
- `xargs` : Convert standard input into command-line arguments for another command.
    - Example: `cat file.txt | xargs rm`
- `ps` : Display currently running processes.
    - `ps -ef` displays all running processes.
- `kill "PID"` : Terminate a process using its Process ID (PID).
- `top` : Display real-time information about running processes and system resource usage.
- `htop` : An interactive version of `top` with a more user-friendly interface.
- `df -h` : Display disk space usage in a human-readable format.
- `du -sh "directory"` : Display the total size of a directory in a human-readable format.
- `tar`
    - `tar -cvf archive.tar directory/` : Create a tar archive.
    - `tar -xvf archive.tar` : Extract a tar archive.
- `zip archive.zip "file_name"` : Compress one or more files into a ZIP archive.
- `unzip archive.zip` : Extract the contents of a ZIP archive.
- `ssh username@hostname` : Securely connect to a remote Linux machine using SSH.
- `scp "file_name" username@hostname:/destination/path` : Securely copy files between computers over SSH.
- `wget "url"` : Download a file from the internet using its URL.
