# Basic Level 1

Start off on: [Direct Link](https://www.hackthissite.org/missions/basic/1/)

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

Solution: Enter in "`e818f8d1`" into the password and click on submit.

![image](https://github.com/user-attachments/assets/593acff8-3ba6-4f21-adcd-fba7e1d08b24)

#

# Basic Level 2 

![image](https://github.com/user-attachments/assets/93136c66-df48-4d6d-b5d3-84bf648e597d)

## Steps: 

Since the prompt said: Sam neglected to upload the password file. There are several outcomes:
- No one can login because password file is missing.
- Anyone can login because password file is missing.

In this case everyone can login. 

Solution: Just click on `submit` without a password and complete the challenge.

![image](https://github.com/user-attachments/assets/faca15ee-56d8-4915-8f12-412f7b132deb)

#

# Basic Level 3

![image](https://github.com/user-attachments/assets/c36b5529-76c5-421e-b2b8-b883a953aa60)

## Steps: 

Since the prompt said the password file is uploaded. I assume that we have to find the password file somewhere
- Right click the box where you put password and click on "Inspect (Q)"

![image](https://github.com/user-attachments/assets/5adf0141-1c36-43d3-a98c-e7f47e273a57)

- The line above where it display the box information in the inspector shows a "hidden file" with value = "password.php".

![image](https://github.com/user-attachments/assets/bb9af45c-ff96-45ef-9aef-7113beeff5ac)

- Now we will put that hidden file directory on the URL
 - https://www.hackthissite.org/missions/basic/3/password.php

Result: Got password = `f19b94c4`

![image](https://github.com/user-attachments/assets/f6bbf096-80db-43ce-939e-42a18dccb159)


Solution: Enter in `f19b94c4` into password and click on submit.

![image](https://github.com/user-attachments/assets/d4bf5ecb-35e4-413a-9d6b-84e9033ef556)

#

# Basic Level 4

![image](https://github.com/user-attachments/assets/11c58645-7850-45f0-ae35-5b7f04c34847)

## Steps: 

Since the prompt said there is a script that email password automatically when clicking on the button "Send password to Sam", I assume we can change the email to myself to get the password.
- Right click the box "Send password to Sam" and click on the Inspect (Q).

![image](https://github.com/user-attachments/assets/8aa23f85-d4ec-4c7b-9a80-4787a0435e79)

- Similar concept on the last challenge, there is a "hidden value" of "sam@hackthissite.org".

![image](https://github.com/user-attachments/assets/435f48e3-e9c0-4039-aec8-d33fd7ce9a14)

- We can change the hidden value to my own email by clicking into it.

![image](https://github.com/user-attachments/assets/21213316-5b21-4156-b2dc-08e9ffffdef4)

- Now click on the box "Send password to Sam".

![image](https://github.com/user-attachments/assets/d55ba293-82d3-4067-8a9c-8a999c49aeb7)

- Go to your own email that you put into the inspector and you will get the password.

![image](https://github.com/user-attachments/assets/a493fd0c-2431-4b41-a23d-106e68a67b6b)

Result: password = `d156d588`

Solution: Enter in `d156d588` into password and click on submit.

![image](https://github.com/user-attachments/assets/6ffc416c-ab66-4c5c-869f-118d0a37386e)

# 

# Level 5

![image](https://github.com/user-attachments/assets/ffe3c383-f3e2-40be-9976-677b62f42e88)

## Steps: 

This is the exact same thing:

- Inspect the the "Same password to Sam" Box
- Change/Edit the hidden value from "sam@hackthissite.org" to your own email.
- Click on the "Send password to Sam".

![image](https://github.com/user-attachments/assets/b62f3611-b36f-4b79-94f1-053bbc2083d6)

- Check your own email.

![image](https://github.com/user-attachments/assets/2f2fdd09-10d1-4674-9baf-336e0ca3c491)

Result: password = `a4fbe76b`

Solution: Enter in `a4fbe76b` into password and click on submit.

![image](https://github.com/user-attachments/assets/59bb8f9a-f8a9-498a-91ab-064e9f26f145)

#

# Level 6

![image](https://github.com/user-attachments/assets/0941ed86-f842-4bf4-b6cb-71298d1e331c)

## Steps: 

This level is just encryption, you can test 1 word at a time to get 0f69:6l?

- By trying one by one, I got the password: `0e4661f8`

Solution: Enter in `0e4661f8` into password and click on submit. 

![image](https://github.com/user-attachments/assets/aa21c023-2d63-40ec-848c-517be049e9cd)

#

# Level 7

![image](https://github.com/user-attachments/assets/055208f3-298a-48e7-a8a1-478a67288100)

## Steps: 

Since the prompt said the output is from the UNIX cal command. We can use command like `&&` and `ls` after giving the year.
- Command: `2024 && ls`

![image](https://github.com/user-attachments/assets/b1ed461b-bbdc-4e62-b933-389deb100910)

- Scroll down to the end and there is a directory called `k1kh31b1n55h.php`

![image](https://github.com/user-attachments/assets/6d868a05-62e8-4913-a755-779b994afced)

- Now we can just go to this directory on the URL.

![image](https://github.com/user-attachments/assets/68786f66-9767-46b5-8828-b3590aef5299)

Result: password = `7707bc62`

Solution: Enter in `7707bc62` into password and click on submit. 

![image](https://github.com/user-attachments/assets/0e66c415-dc18-45bd-bbe4-df4602b6c253)

#

# Level 8

![image](https://github.com/user-attachments/assets/93ce15b0-367f-4558-97ce-a9e783051548)


`<!--#exec cmd="ls ../"-->`

# Key Takeaway:

## 1. View Page Source or Inspect (Q) are important, sometimes there are clues that the coder leave behind, such as comments.

- For html: `<!-- ... -->` is a comment.

## 2. Missing password file can be a very serious vulnerability because if the code is default allow behavior, everyone can login.

## 3. Inspect (Q) can show hidden file sometimes.

## 4 and 5. We can edit value on the hidden input type. 

## 6. This is more like a Bruteforce thing.

## 7. We can break the command with `&&` and then another command like `ls`
