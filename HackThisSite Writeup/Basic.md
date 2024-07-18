# Basic Level 1

[Direct Link](https://www.hackthissite.org/missions/basic/1/)

![image](https://github.com/user-attachments/assets/6ac143ac-5bc6-4645-afa9-63a65a5239f6)

## Steps: 

Right-click on the site, either go "View Page Source" or "Inspect (Q)"

![image](https://github.com/user-attachments/assets/93ba3c8c-fb14-46d0-bef8-aa008cae5ca6)

For "View Page Source"
- Scroll down to line 175: "`<!--the first few levels are extremely easy: password is e818f8d1-->`"
 
![image](https://github.com/user-attachments/assets/03dc978a-6a25-438a-9536-5f301ce75335)

For "Inspect (Q)"
- Right-click on password input box and select "Inspect (Q).
- Scroll down and you will see: "`<!--the first few levels are extremely easy: password is e818f8d1-->`"
 
![image](https://github.com/user-attachments/assets/ff4e08f2-c868-495e-8cf2-0fd395a26447)

Solution: Enter in "`e818f8d1`" into the password and submit.

![image](https://github.com/user-attachments/assets/593acff8-3ba6-4f21-adcd-fba7e1d08b24)

#

# Basic Level 2 

![image](https://github.com/user-attachments/assets/93136c66-df48-4d6d-b5d3-84bf648e597d)

Since the prompt said: Sam neglected to upload the password file. There are several outcomes:
- No one can login because password file is missing.
- Everyone can login because password file is missing.

In this case everyone can login. 

Solution: Just click on `submit` without a password and complete the challenge.

![image](https://github.com/user-attachments/assets/faca15ee-56d8-4915-8f12-412f7b132deb)

#

# Basic Level 3




# Key Takeaway:

## 1. View Page Source or Inspect (Q) are important, sometimes there are clues that the coder leave behind, such as comments.

- For html: `<!-- ... -->` is a comment.

## 2. Missing password file can be a very serious vulnerability because if the code is default allow behavior, everyone can login.
