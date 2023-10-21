# Mastering Bash Shell Script

Bash scripting plays a crucial role in cybersecurity due to its versatility and automation capabilities. Cybersecurity professionals use Bash scripts to automate repetitive tasks like log analysis, vulnerability scanning, and system monitoring. These scripts enable efficient response to security incidents, streamline security checks, and help in maintaining the integrity of systems and networks. Additionally, Bash scripts are essential for creating custom security tools and performing routine security assessments, enhancing overall defense against cyber threats. Their flexibility and the ability to adapt to changing security needs make Bash scripts an integral component of a cybersecurity professional's toolkit.

<h2></h2>

<h2>Prerequisites</h2>

- Register for a trial account on DigitalOcean and deploy a Linux Virtual Machine (VM). [Tutorial Here](https://github.com/jefftsui1/Cybersecurity-Home-Labs/blob/main/Virtual-Machine/DigitalOcean/Linux.md)

- Download PuTTY for connecting to the Linux Virtual Machine (VM). [Tutorial Here](https://github.com/jefftsui1/Cybersecurity-Home-Labs/blob/main/Virtual-Machine/PuTTY/PuTTY.md)

<h2></h2>

<h2>Solve 100 Hands-On Tasks and 13 Hand-Ons Mini Projects</h2>

- 25 Basic Bash Commands Hands-On Tasks.

- 25 Intermediate Commands Hands-On Tasks.

- 25 Basic Bash Scripting Hands-On Tasks.

- 25 Intermediate Bash Scripting Hands-On Tasks.

- 13 Bash Scripting Hands-On Projects.

<h2></h2>

<h2>Three Bash Commands Overview:</h2>

<h3>Grep Command</h3>

- Grep Command: Filter or search of a file for a "particular pattern or characters". Then display all lines that contain the pattern.

- Useful: It can be quite challenging to locate a particular "term" within extensive log files.

- Use: Easily find out some specific keywords to the huge files. 

Example:

On PuTTY in order to see what files is in the /var/log directory:

- Type in: ```ls -lrt /var/log```. 
  - ls: list command.
  - -lrt: long list, reverse ordering, sort by time.
  - /var/log: directory for storing logs in linux.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/7tB3N4D.png" height="60%" width="60%" alt=""/>
<br />

Looking into file "dnf.log" with grep command with keyword "error".

- Type in: ```grep "error" /var/log/dnf.log```.
  - Output: Display all the lines that contains the keyword "error" (coded in red) within the "dnf.log" file.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/2wLapXa.png" height="60%" width="60%" alt=""/>
<br />

To only count the "total number of lines" that contains the "error" keyword. Use ```-c```.

- Type in: ```grep -c "error" /var/log/dnf.log```.
  - Output: 16. Meaning in the dnf.log file, only 16 lines contains the keyword "error".

<p align="center">
<br/>
<img src="https://i.imgur.com/eyjVras.png" height="60%" width="60%" alt=""/>
<br />

To count the "total number of lines" that does not contain the "error" keyword. Use  ```-c -v```

- Type in: ```grep -c -v "error" /var/log/dnf.log```.
  - Output: 398. Meaning in the dnf.log file, 389 lines does not contain the keyword "error".

<p align="center">
<br/>
<img src="https://i.imgur.com/OHbhGsn.png" height="60%" width="60%" alt=""/>
<br />

To ignore lowercase or uppercase within the "error" keyword. Use ```-i```. 
 
- Type in: ```grep -i "error" /var/log/dnf.log```.
- Output: Display all the line that contains the keyword "error" (coded in red) within the "dnf.log" file without case sensitive.

Count

- Type in: ```grep -c -i "error" /var/log/dnf.log```.
- Output: 18. Two more lines than without "-i".

<p align="center">
<br/>
<img src="https://i.imgur.com/3Vha7zJ.png" height="60%" width="60%" alt=""/>
<br />

<h2></h2>

<h3>Sed Command</h3>

- Sed Command: Stands for Stream EDitor, can perform functions like searching, replacing a context and finding some files with insertions and deletions.

- Useful: When doing a lot of changing within a file without doing it manually.

- Use: Substitution, find, replace the content within the files.

Example:

On PuTTY in order to create a new txt file named "dummy":

- Type in: ```vi dummy.txt``` and Enter.
  - vi: visual editor, can edit an existing file or create a new file from scratch.
  - dummy.txt: using visual editor to create a txt file named "dummy".

<p align="center">
<br/>
<img src="https://i.imgur.com/67sjFqp.png" height="60%" width="60%" alt=""/>
<br />

- Type in random words inside the dummy.txt
- To save type in: ```:wq!``` and Enter.

<p align="center">
<br/>
<img src="https://i.imgur.com/AAs2eqm.png" height="60%" width="60%" alt=""/>
<br />

To view the content of the "dummy.txt" Use ```cat```.

- Type in: ```cat dummy.txt```.

<p align="center">
<br/>
<img src="https://i.imgur.com/DIbH0Hh.png" height="60%" width="60%" alt=""/>
<br />

To replace "bash" with "bashscripting" in dummy.txt using sed command.

- Type in: ```sed 's/bash/bashscripting/g' dummy.txt```.
  - sed: Stream EDitor command.
  - s: substitute.
  - /bash: the string you want it to be replace.
  - /bashscript: the string you want to replace with.
  - /g: global, string that match in the .txt file will be replaced.
    - 's/bash/bashscripting/g' must be in ' '.
  - dummy.txt: the file you want to modify.

<p align="center">
<br/>
<img src="https://i.imgur.com/MwM0d9J.png" height="60%" width="60%" alt=""/>
<br />

- But using ```sed 's/bash/bashscripting/g' dummy.txt``` will not be saved.
- ```cat dummy.txt``` to check.

<p align="center">
<br/>
<img src="https://i.imgur.com/GaL9KI6.png" height="60%" width="60%" alt=""/>
<br />

In order to save with sed command

- Type in: ```sed -i 's/bash/bashscripting/g' dummy.txt```.
  - -i: edit file in place.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/NWATSk9.png" height="60%" width="60%" alt=""/>
<br />

To replace the first occurence of each line. (Changing from bashscripting back to bash for the first occurence)

- Type in: ```sed -i 's/bashscripting/bash/1' dummy.txt```.
  - 1: first occurence of each line.

<p align="center">
<br/>
<img src="https://i.imgur.com/JxTzH8G.png" height="60%" width="60%" alt=""/>
<br />

Can use it with the any occurance.
- Type in: ```sed -i 's/bashscripting/jeff/2' dummy.txt```.

<p align="center">
<br/>
<img src="https://i.imgur.com/x1xFcUw.png" height="60%" width="60%" alt=""/>
<br />

 
- 
