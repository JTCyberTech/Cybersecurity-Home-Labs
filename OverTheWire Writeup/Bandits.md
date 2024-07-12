# Level 0

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/5c3babd0-a713-4a61-b0cc-d4375f0339cf)

## Command Steps: 

In order to login to the ssh of bandit0:
- ssh bandit0@bandit.labs.overthewire.org -p 2220
- password: bandit0 

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/38b3d3b5-ded1-4258-9f11-d3c7a3c18696)

#

# Level 0 -> 1

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/400f1e02-b5e0-4fb3-a4f2-d581d6ac53aa)

## Command Steps: 

In order to login to the ssh of bandit0:
- ssh into bandit0: ssh bandit0@bandit.labs.overthewire.org -p 2220
- Using password: bandit0

In order to find, locate, and read the file "readme":
- Use command "```ls```" to **see what file or directory** is in the bandit0 ssh shell.
  - Found a file called "readme"
- Use command "```cat```" to **read** the file "readme".
  - Command: "```cat``` readme"
- Found password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/4c1c0d1e-2f85-44bf-951a-b8a333023954)

#

# Level 1 -> 2

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/56ef3ac3-7cf7-47d5-80c6-375cd40c5d12)

## Command Steps: 

In order to login to the ssh of bandit1:
- Type in: "exit" to exit bandit0@bandit ssh
- ssh into bandit1: ssh bandit1@bandit.labs.overthewire.org -p 2220
- Using password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

In order to find, locate, and read the file "-":
- Use command "```ls```" to see what file or directory is in the bandit1 ssh shell.
  - Found a file called "-"
- Use command "```cat```" to try to read the file "-"
  - Command: "```cat``` -"
  - Nothing happened because "-" is treated as a start of an **option**. Press "Ctrl + z" to stop
- Use command "```cd``` -" to **try to change directory** into "-"
  - Result: "```cd``` -" cannot be run because cd doesn't have options. (e.g "cd -la", options doesn't exist for cd)
  - In order to read "-" we need to use ```cat``` and add "./" in front of "-". Because "./" in front tells command that "-" is a filename not an option
  - Command:  "```cat``` ./-"
- Found password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
 
![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/3bc61e17-1b96-490e-a263-643aae2f3510)

#

# Level 2 -> 3

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/a229a796-d02a-4b71-843c-ba9d5c16a261)

## Command Steps: 

In order to login to the ssh of bandit2:
- Type in: "exit" to exit bandit1@bandit ssh
- ssh into bandit2: ssh bandit2@bandit.labs.overthewire.org -p 2220
- Using password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

In order to find, locate, and read the file "spaces in this filename":
- Use command "```ls``` to see what file or directory is in the bandit2 ssh shell.
  - Found the file called "spaces in this filename"
- Use command "```file``` to see what kind of file is "spaces in this filename":
  - Command: ```file "spaces in this filename"```
  - Found: "ASCII text" meaning American Standard Code for Information Interchange; or **Plain Text**.
- Use command "```cat```" to read the file "spaces in this filename".
  - Command: "```cat``` "spaces in this filename" "
  - Note: we have to add " " to my space in this filename to work.
- Found password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/417e991f-d17e-4fe4-b5c6-e7f9b86a8949)

#

# Level 3 -> 4

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/54ca22c7-099d-48b3-93e8-64e66e27d8aa)

## Command Steps: 

In order to login to the ssh of bandit3:
- Type in: "exit" to exit bandit2@bandit ssh
- ssh into bandit3: ssh bandit3@bandit.labs.overthewire.org -p 2220
- Using password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

In order to change directory into the inhere directory:
- Use command: `ls`  to list what files or directory is in the shell.
  - Found there is a "inhere" directory.
- Use command: `cd` to change directory into "inhere.
  - Command: "`cd` inhere/

In order to get the password in the hidden file in the inhere directory:
- Use command `ls -la`: to list what files or directory is in the inhere directory.
  - `-l`: long list format.
  - `-a`: Include hidden file.
  - `-la`: combine of both.
  - Result: Found a file "...Hiding-From-You"
- Use command `file` to see what type of file is "...Hiding-From-You"
  - Command: `file` "...Hiding-From-You"
  - Result: ...Hiding-From-You file is a ASCII text file.
- Use command `cat` to read what is in the ASCII text file.
  - Command: `cat` "...Hiding-From-You"
- Found password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/88ce834a-a971-4a11-a464-2c9b42d8dd5e)

#

# Level 4 -> 5

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/db49c0bd-432a-44ca-81f7-fff46d7a996c)

## Command Steps: 

In order to login to the ssh of bandit4:
- Type in: "exit" to exit bandit3@bandit ssh
- ssh into bandit4: ssh bandit4@bandit.labs.overthewire.org -p 2220
- Using password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

In order to change directory into the inhere directory:
- Use command: `ls`  to list what files or directory is in the shell.
  - Found there is a "inhere" directory.
- Use command: `cd` to change directory into "inhere.
  - Command: "`cd` inhere/
 
In order to get the password in the human-readable file in the inhere directory:
- Use command: `ls -la`: to list what files or directory is in the inhere directory.
  - `-l`: long list format.
  - `-a`: Include hidden file.
  - `-la`: combine of both.
  - Result: Found a file "-file00 to -file09"
- Use command: `file` to see what type of file are all the files in the inhere directory.
  - Command: `file` ./*
    - `./*` : to list all files and directory in the current directory.
  - Result: -files07 is the only one that is ASCII text, others are not readable.
- Use command: `cat` to read what is in the ASCII text file.
  - Command: `cat` ./-file07
    - Can't just do `cat` -file07 because -file07 will be treated as a unrecogizable option for cat.
- Found password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

Side note: 
- Other files are unreadable: e.g "-file00 and -file03"

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/8077c94d-1f03-4f34-bafc-02f19f552be4)

#

# Level 5 -> 6

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/24c3c182-624c-4f31-a2f5-ad0d580732a2)

## Command Steps: 

In order to login to the ssh of bandit5:
- Type in: "exit" to exit bandit4@bandit ssh
- ssh into bandit5: ssh bandit5@bandit.labs.overthewire.org -p 2220
- Using password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

In order to change directory into the inhere directory:
- Use command: `ls`  to list what files or directory is in the shell.
  - Found there is a "inhere" directory.
- Use command: `cd` to change directory into "inhere.
  - Command: "`cd` inhere/
 
In order to get the password in the human-readable file in the inhere directory:
- Use command: `ls -la`: to list what files or directory is in the inhere directory.
  - Result: Found "maybehere00 to maybehere19"
- Use command `file ./* to see what are the file types or directory for "maybehere00 to maybehere19"
  - Result: They are all directory.
- Since it's all directory it's not help.

Using the `find` command to find a not executable file in the inhere directory:
- Use Command "`find` . -type f ! -executable"
  - `find`: main command used to search for files and directories in a directory hierarchy.
  - `.`: specifies the starting point for the search. This case means the current directory (inhere/).
  - `-type f`: restricts the search to files only (not directories). [f: stands for "files"].
  - `! executable`: [`!`: negation operator, inverts the test that follows it] [`-executable`: checks if a file is executable] [`! -executable` means "not executable]
Result: A bunch of random files from all directory from maybehere00 to maybehere19.

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/62cc6397-87c2-4e34-b990-b9c7c18d2327)


Using the `find` command to find 1033 bytes in size in the inhere directory:
- Use command: "`find` . -type f -size 1033c" to find a file within the inhere directory that is 1033 bytes in size.
  - `find`: main command used to search for files and directories in a directory hierarchy.
  - `.`: specifies the starting point for the search. This case means the current directory (inhere/).
  - `-type f`: restricts the search to files only (not directories). [f: stands for "files"].
  - `-size 1033c`: [`-size`: specifies the size of the files to search for] [`1033c`: the exact size in bytes, `c`: character or bytes].
- Result: ./maybehere07/.file2

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/c3f170fb-6b47-44fa-b664-5bb172b9a6cf)

Combine all the commands:
- Command: `find` . -type f ! -executable -size 1033c

In order to have a command that satisfy all three condition:
- human-readable
- 1033 bytes in size
- not executable

We have to do a For loop:
- Command:
- > for file in $(find . -type f -size 1033c ! -executable);
- > do file "$file"
- > done
  
Explanation of the For loop:
- `for file in $(...)`: iterates each file name found by the `find` command inside `$(...)`.
- `do ... done`: Encloses the commands to be executed for each iteration of the loop.
- `file "$file"`:
- "$file" = file in $(find . -type f -size 1033c ! -executable)

Result: Found one file "./maybehere07/.file2: ASCII text, with very long lines (1000)"

![image](https://github.com/user-attachments/assets/ef162f61-b647-43c5-ad64-2b4417f58d0d)

Use `cat` command to read the ./maybehere07/.file2
- Command: `cat` ./maybehere07/.file2
- Found password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

![image](https://github.com/user-attachments/assets/f39dff12-a045-4cda-b18f-a5890801de60)


#

# Level 6 -> 7

![image](https://github.com/user-attachments/assets/a0a5d4f3-b9e9-485f-bd9f-4fffbca0435e)

## Command Steps: 

In order to login to the ssh of bandit6:
- Type in: "exit" to exit bandit5@bandit ssh
- ssh into bandit6: ssh bandit6@bandit.labs.overthewire.org -p 2220
- Using password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

Since the password is stored somewhere on the server:
- We have to use `cd` command to change to the server directory.
- Command: `cd` /

![image](https://github.com/user-attachments/assets/1b24e642-da6c-46cd-b3fe-03b8c2248dfb)

Since the password have 3 properties:
- Owned by user bandit7
- Owned by group bandit6
- 33 bytes in size

We have to use the `find` command with all three properties:
- Command: `find` . -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
- Result: ./var/lib/dpkg/info/bandit7.password


Explanation: 
- `find .`: Start searching in the current directory. (in this case is the root directory or / directory)
- `-type f`: Only include regular files in the search.
- `-user bandit7`: Matches the properties of "Owned by user bandit7".
- `-group bandit6`: Matches the properties of "Owned by group bandit6".
- `-size 33c`: Mataches the properties of "33 bytes in size".
- `2>/dev/null`: Redirect any error message (e.g. "Permission denied") to `/dev/null` to avoid cluttering the output.

![image](https://github.com/user-attachments/assets/dae7c363-3cf0-44ef-b14c-90bb9cc64e1e)

Read the file by using `cat` command:
- Command: cat ./var/lib/dpkg/info/bandit7.password
- Found password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

![image](https://github.com/user-attachments/assets/cec14966-0da3-4335-8abe-2188932ab568)

#

# Level 7 -> 8

![image](https://github.com/user-attachments/assets/bc3a1ceb-6964-47b6-bfbe-9490d3be144b)

## Command Steps: 

In order to login to the ssh of bandit7:
- Type in: "exit" to exit bandit6@bandit ssh
- ssh into bandit7: ssh bandit7@bandit.labs.overthewire.org -p 2220
- Using password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

In order to get the password inside of the data.txt file, we will need to use the `grep` command.
- Command: `grep` "millionth" data.txt
- Found password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

Explanation: 
- `grep`: "Global regular expression print." Used to search plain-text data sets for lines that match a regular expression.
- `"millionth"`: Search pattern, in this case: the literal string "millionth".
  - `grep` "millionth": will look for lines that contain this exact string.
- `data.txt`: File to be search in with the grep comman.

![image](https://github.com/user-attachments/assets/ae73aeec-abff-4bf5-ac19-281ac8bd6349)

#

# Level 8 -> 9

![image](https://github.com/user-attachments/assets/0b80af7c-b5ce-472b-9f61-260c145de0b3)

## Command Steps: 

In order to login to the ssh of bandit8:
- Type in: "exit" to exit bandit7@bandit ssh
- ssh into bandit8: ssh bandit8@bandit.labs.overthewire.org -p 2220
- Using password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

In order to get the only line of text that occurs once in data.txt file, we have to use `sort` and `unqi` commands.
- Command: `sort` data.txt | `uniq` -u
- Found password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

Explanation: 
- `sort` data.txt: Sorts the lines in "data.txt" file, making identical lines adjacent to each other.
- `|` (Pipe): Passes the sorted output to the next command.
- `uniq -u`: Filters out lines that are repeated, leaving only unique lines.

![image](https://github.com/user-attachments/assets/115b7525-f875-4cbc-b7eb-bf59d3af3e36)

#

# Level 9 -> 10

![image](https://github.com/user-attachments/assets/0c1d297f-0c7f-4f44-a16f-d9aad16febcd)

## Command Steps: 

In order to login to the ssh of bandit9:
- Type in: "exit" to exit bandit8@bandit ssh
- ssh into bandit9: ssh bandit9@bandit.labs.overthewire.org -p 2220
- Using password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

In order to get the password that is human-readable strings and preceded by several "=" characters, we have to use `strings` and `grep` commands.
- Command: `strings` data.txt | grep "==="
- Found password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

Explanation:
- `strings data.txt`: Command that extracts human readable strings from binary files or files with non-text content. Output all human readable strings found in "data.txt".
- `|` (Pipe): Takes the output of command `strings` and passes it as input to `grep` command.
- `grep "==="`: Searches for lines that contains "===" characters pattern.

![image](https://github.com/user-attachments/assets/4c089920-13ce-48fa-af99-fb0ecd85e71b)

#

# Level 10 -> 11

![image](https://github.com/user-attachments/assets/230c95c9-e141-484e-8e7b-05ba38a8fcc8)

## Command Steps: 

In order to login to the ssh of bandit10:
- Type in: "exit" to exit bandit9@bandit ssh
- ssh into bandit10: ssh bandit10@bandit.labs.overthewire.org -p 2220
- Using password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

In order to get the password from data.txt that contains base64 encoded, we have to use the `base64` command:
- Command: `base64` -d data.txt
- Found password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

Explanation:
- `base64 -d data.txt`: `-d` = decodes, decodes the base64 encoded data in "data.txt".

![image](https://github.com/user-attachments/assets/a6ef83f9-7ae0-4f6f-a351-6bd4fad3d06e)

#

# Level 11 -> 12

![image](https://github.com/user-attachments/assets/6cba52d5-23ec-4e5d-a247-3b25b5ab8408)

## Command Steps: 

In order to login to the ssh of bandit11:
- Type in: "exit" to exit bandit10@bandit ssh
- ssh into bandit11: ssh bandit11@bandit.labs.overthewire.org -p 2220
- Using password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

In order to read data.txt with A-Z and a-z letter rotated by 13 position, we have to use `cat` and `tr` commands:
- Command: `cat` data.txt | `tr` 'A-Za-z' 'N-ZA-Mn-za-m'
- Found password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

Explanation:
- `cat data.txt`: concatenate, used to display the contents in data.txt file.
- `|` (Pipe): Shell operator, takes output of the command on left and use it as input command to the right.
- `tr 'A-Za-z' 'N-ZA-Mn-za-m'`:
  - `tr`: A command that translates or deletes character from the input it recieves.
  - `A-Za-z`: First set of characters that we want to translate. Includes all uppercase (A-Z) and all lowercase (a-z).
  - `N-ZA-Mn-za-m`: Second set of characters that we want to translate to. It represent the alphabet rotated by 13 positions:
    - ROT13 transmation: each letter is replaced by the letter 13 positions after its position in the alphabet; 'A' = 'N', 'M' = 'Z'.
   
![image](https://github.com/user-attachments/assets/a3f1129d-ed57-4464-8a9b-ab6a4681e554)

#

# Level 12 -> 13

![image](https://github.com/user-attachments/assets/529ebe90-39d0-4bd9-8520-473b985791c3)

## Command Steps: 

In order to login to the ssh of bandit11:
- Type in: "exit" to exit bandit11@bandit ssh
- ssh into bandit12: ssh bandit12@bandit.labs.overthewire.org -p 2220
- Using password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

In order to repeatly decompresses the hexdump data.txt file, we will need to use `tar`, `gzip`, and `bzip2`.

First we need to create a temporary directory under /tmp because we don't have permission to create anything in the current directory:
- Command: `newdata=$(mktemp -d)`
  - `newdata=`: Assigning output of the `mktemp -d` command to variable name "newdata".
  - `$(...)`: Takes output of the command inside the () and substitutes/save it as "newdata".
  - `mktemp`: A Command used to create a temporary file or direcotry.
    - `-d`: Option of `mktemp`, tells `mktemp` to create a directory instead of a file.
 
Next we have to copy the data.txt file in the current directory into the temporary directory that we just created by using the `cp` command:
- Command: `cp data.txt $newdata`
  - `cp`: Command used to copy files or directories.
  - `data.txt`: The source file you want to copy.
  - `$newdata`: Destination where you want to copy the file to. (In this case: the new temporary directory)

Next we have to change directory into the new temporary directory by using `cd` command:
- Command: `cd $newdata`

![image](https://github.com/user-attachments/assets/a6c8d7f4-2c82-4a4a-a643-def88fb200e4)

Afterward, we need to use the `xxd` command to convert the Hexdump file (data.txt) into Binary:
- Command: `xxd -r data.txt data.bin`
  - `xxd`: Command create a hexdump from given file or input. Or reverse hexdump file back into binary form.
    - `-r`: Option of `xxd`, stands for "reverse", tells `xxd` to convert hexdump back to binary form.
  - `data.txt`: The input file that contains the hexdump you want to convert back into binary.
  - `data.bin`: The output file that will contain the binary result from `xxd -r` command.
 
![image](https://github.com/user-attachments/assets/be2792d0-2bc8-4eff-90e0-c43645c96b4a)

Next we need to check the file type of data.bin by using `file` command:
- Command: `file data.bin`
- Result: gzip compressed.

![image](https://github.com/user-attachments/assets/147a10ed-fe5a-42f7-ac4b-4e127ab1a441)

Next since it's gzip compressed data, we need to rename the file into gzip file with `mv` command and decompress it with the `gzip` command:
- Command: `mv data.bin data.gz`
  - `mv`: Command used to move or rename files and directories.
  - `data.bin`: Source file in the current directory that needed to be rename.
  - `data.gz`: Output file that got rename into, became a different file type (Gzip file).
- Command: `gzip -d data.gz`
  - `gzip`: Command used for compression and decompression of Gzip file.
    - `-d`: Option for `gzip`, stand for decompress.
  - `data.gz`: Input file that you want to decompress.
- Result: "data.gz" file became "data" file that is Bzip2.

![image](https://github.com/user-attachments/assets/1d22f157-348f-4855-a3bc-c878d50d2359)

Next since it's bzip2 compressed data, we need to rename the file into bzip2 file with `mv` command and decompress it with the `bzip2` command:
- Command: `mv data data.bz2`
  - bzip2's file name = bz2
- Command: `bzip2 -d data.bz2`
  - `bzip2`: Command used for compressing or decompressing files using Burrow-Wheeler block-sorting text compression alogrithm and Huffman coding (Bzip2).
    - `-d`: Option for `bzip2, stand for decompress.
  - `data.bz2`: Input file that you want to decompress.
- Result: "data.bz2" file became "data" file that is Gzip.

![image](https://github.com/user-attachments/assets/2c3a5ae4-ab4e-45e2-8372-a7b7e59d6cb1)

**Repeat the Gzip Decompress Again**
- Result: "data.gz" file became "data" file that is tar.


FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
