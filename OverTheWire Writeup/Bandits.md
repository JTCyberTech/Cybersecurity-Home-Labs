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

In order to locate and read the file "readme":
- Use command "```ls```" to **see what file or directory** is in the bandit0 ssh shell.
  - Found a file called "readme"
- Use command "```cat``` readme" to **read** the file "readme".
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

In order to find and locate the file "-":
- Use command "```ls```" to see what file or directory is in the bandit1 ssh shell.
  - Found a file called "-"
- Use command "```cat``` -" to try to read the file "-"
  - Nothing happened. Press "Ctrl + z" to stop
- Use command "```cd``` -" to **try to change directory** into "-"
  - Result: "-" it's a **bash** script.
  - In order to read bash script we need to use ```cat``` and add "./" in front of "-"
  - ```cat``` ./-
  - Found password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
 
![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/3bc61e17-1b96-490e-a263-643aae2f3510)

#

# Level 2 -> 3

![image](https://github.com/JTCyberTech/Cybersecurity-Home-Labs/assets/46698661/27a3aafd-1790-424c-916a-e18ec9097630)

## Command Steps: 

In order to login to the ssh of bandit2:
- Type in: "exit" to exit bandit1@bandit ssh
- ssh into bandit2: ssh bandit12@bandit.labs.overthewire.org -p 2220
- Using password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
- 
