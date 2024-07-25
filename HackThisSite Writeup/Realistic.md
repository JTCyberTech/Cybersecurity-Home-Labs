# Realistic Level 1

![image](https://github.com/user-attachments/assets/707e64a4-af3e-4623-85d7-5e31c42f213b)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/1/)

![image](https://github.com/user-attachments/assets/b8a49a19-4ede-41b9-88ad-4218f167bf8d)

[Realistic 1 - WebSite](https://www.hackthissite.org/missions/realistic/1/)

## Steps:

Since the prompt told us to hack the site and make the band "Raging Inferno" to the top.

We can tamper the element by right clicking the score next to the vote button > click on inspect.

![image](https://github.com/user-attachments/assets/e8627a13-6a2e-474b-a3a5-8f919adad3f0)


Expand: the `"<select name="vote"> == $0`
- Change value="5" into value="5000000"

![image](https://github.com/user-attachments/assets/ccfb3bbf-0cb9-4fc5-9fd1-97e3a0b7fbe9)

Select 5 on the webpage and click on vote.

#

# Realistic Level 2

![image](https://github.com/user-attachments/assets/13dbe64a-1160-4fba-b185-6991bf8470bd)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/2/)

![image](https://github.com/user-attachments/assets/62c7d5f7-26af-4cfc-9e7e-c837ddf0f457)

[Realistic 2 - WebSite](https://www.hackthissite.org/missions/realistic/2/)

## Steps:

First we inspect the page by right-clicking on the page > click on "View page source"

![image](https://github.com/user-attachments/assets/47aacc58-88b5-4363-8e41-963649fdeda9)

On the page source, we can see that there is a hidden link called update: /missions/realistic/2/update.php
- We will click on it.

![image](https://github.com/user-attachments/assets/c985ce2f-accc-4044-a264-9540877c8f92)

The hidden link bring us to a login page.

![image](https://github.com/user-attachments/assets/0b8dd7b1-e333-479c-aca5-74ce0c999c01)

We will use SQLi to bypass the login page.
- Most basic SQLi = `' OR 1=1 --`

Explanation:

`' OR 1=1 --`
- `'` (Single Quote): Used to close an open string in SQL. If the input is improperly sanitized, it can terminate the intended SQL string.
- `OR 1=1`: Logical condition that always evalutes to true. This part of the injection makes the whole condition  true regardless of the actual data in the database.
- `--` (Double Hyphen): Comment indicator in SQL. Everything after `--` is ignored by SQL engine.

![image](https://github.com/user-attachments/assets/0f5e4bb4-da20-413a-88a7-2d36944924f7)

Since it ignores everything after --, we don't have to put anything on the password box and just hit submit.

#

# Realistic Level 3

![image](https://github.com/user-attachments/assets/90735a53-1f7b-4b53-ad6d-c53f5f3ef1ef)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/3/)

![image](https://github.com/user-attachments/assets/162776be-99bc-48e8-b2aa-0cd2d7ad6f7b)

[Realistic 3 - WebSite](https://www.hackthissite.org/missions/realistic/3/)

## Steps:

If we Inspect on the website, we can see the comment: 

`<!--Note to the webmasterThis website has been hacked, but not totally destroyed. The old website is still up. I simply copied the old index.html file to oldindex.html and remade this one. Sorry about the inconvenience.-->`


- Right-Click on the website > Click on "Inspect".

![image](https://github.com/user-attachments/assets/da41832f-524b-4719-8866-01cc7f4277cd)

- Inspect element have comment start with: "<!--...-->"

![image](https://github.com/user-attachments/assets/e5d359f8-3b70-4284-8468-296ae89003b5)


We found out that there is a file call "oldindex.html" that is created by copying the original "index.html" file.

- Type in the URL: `https://www.hackthissite.org/missions/realistic/3/oldindex.html`

![image](https://github.com/user-attachments/assets/c6a36621-615b-44ca-98e9-0d9a8ab2192a)

We will now look at the website to see what kind of stuff we can do with it.

- There are two button in the original web page: "Read The Poetry" and "Submit Poetry".

  - Read the Poetry: We can click on the poem and read it.

![image](https://github.com/user-attachments/assets/34d51647-266a-4cbc-ad3c-4367c65b6b51)

  - Submit Poetry: We can write the name of the poem and the details of the poem then click on the "add poem" button. And it will be uploaded to the website.

![image](https://github.com/user-attachments/assets/3f7df8b7-4fd9-4a69-afbe-31de70a7ffad)

I will try to add a poem to see what it does:

![image](https://github.com/user-attachments/assets/20d4ee25-99c3-465a-ad0a-aa33e19f4007)

- Result: `Your poem was successfully added. Thank you for your contributions`
  - URL: https://www.hackthissite.org/missions/realistic/3/submitpoems2.php
 
![image](https://github.com/user-attachments/assets/636f1a16-a875-4911-814f-9f7e5288d097)


#

# Realistic Level 5

![image](https://github.com/user-attachments/assets/2a0daef6-0e09-4c77-817e-9eaae18ede8c)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/5/)

![image](https://github.com/user-attachments/assets/c9e7c9bd-3b6c-4699-905a-7214c006bcf8)

[Site](https://www.hackthissite.org/missions/realistic/5/)

## Steps:

First thing that I did is check out if there is `robots.txt` page on the website.
- URL: `https://www.hackthissite.org/missions/realistic/5/robots.txt`

![image](https://github.com/user-attachments/assets/4d356ec8-9e3b-4447-83fa-3fbcc36caa74)

Robot.txt page gave me two clues; pages: `/lib` and `/secret`. I will explore the `/lib` first.
- I downloaded the hash file but then it's not something that can be readable.

![image](https://github.com/user-attachments/assets/4619ce7d-7f81-4861-abfc-fe1ced78849a)

On the second page `/secret`, there are two .php pages: `admin.bak.php` and `admin.php`:

![image](https://github.com/user-attachments/assets/304b0366-8ae5-4baa-b8f4-2d2fbf1376a2)

Clicking on each of the .php: 

- /admin.bak.php: have a hash value of `ebf7855722651449e5e1e71bf572261d`.

![image](https://github.com/user-attachments/assets/f08a9ef6-668f-42d3-b105-d40d528f262e)

- /admin.php just said "Invalid Password".

![image](https://github.com/user-attachments/assets/5401ab39-f637-44eb-8f27-664a3490e293)

Now, I used John the Ripper on Terminal to crack the hash:

In order to do this I have to save the hash `ebf7855722651449e5e1e71bf572261d` into a Text Editor on Desktop of my Linux VM named "Hash_Value".

![image](https://github.com/user-attachments/assets/14b1e1c0-8932-4a70-a179-359a3f629066)

Next I open up terminal and use the John the Ripper Command:
- Command: `John --format=RAW-md5 Desktop/Hash_Value`: Didn't work so I will try the md4 version because the prompt said it's 10 years old and outdated.
- Command: `John --format=RAW-md4 Desktop/Hash_Value`

Found the password to be: `13af6`

![image](https://github.com/user-attachments/assets/987151b7-56d1-444c-ac7a-1fd18a62a07c)

Now we can go back to the main website and click on Database and enter in the password: `13af6`

![image](https://github.com/user-attachments/assets/af16899e-fae4-4c22-aa23-ee16e9455507)

![image](https://github.com/user-attachments/assets/1ca73d77-387c-4e63-b71b-4117b17ded93)

#

# Realistic Level 6 

![image](https://github.com/user-attachments/assets/703c8c7a-a630-41c8-9096-9db2e99c6c96)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/6/)

![image](![image](https://github.com/user-attachments/assets/584fd64b-bfa5-4fd0-a579-6d0a8e67592e))

[Site](https://www.hackthissite.org/missions/realistic/6/)

## Steps:


## Steps:

view-source:https://www.hackthissite.org/missions/realistic/7/showimages.php?file=/images/admin/.htpasswd



# Key Takeaway:

## 1. We can tamper the score of an element by going into inspect element.

## 2. Most basic SQL injection: `' OR 1=1 --`

## 5. /robots.txt; john --format=RAW-md4 [file]; we can use --show on john to show cracked password from before. 
