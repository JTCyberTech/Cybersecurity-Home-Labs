# Realistic Level 1

![image](https://github.com/user-attachments/assets/707e64a4-af3e-4623-85d7-5e31c42f213b)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/1/)

![image](https://github.com/user-attachments/assets/b8a49a19-4ede-41b9-88ad-4218f167bf8d)

[Realistic 1 - WebSite](https://www.hackthissite.org/missions/realistic/1/)

## Steps:

1. Since the prompt told us to hack the site and make the band "Raging Inferno" to the top.

- We can temper the element by right clicking the score next to the vote button > click on inspect.

![image](https://github.com/user-attachments/assets/e8627a13-6a2e-474b-a3a5-8f919adad3f0)

2. Tempering the elements:

- Expand: the `"<select name="vote"> == $0`
- Change value="5" into value="5000000"

![image](https://github.com/user-attachments/assets/ccfb3bbf-0cb9-4fc5-9fd1-97e3a0b7fbe9)

3. Select 5 on the webpage and click on vote and finish the challenge.

![image](https://github.com/user-attachments/assets/8897ef7f-dee8-4f02-9132-a20bc4b9506f)


#

# Realistic Level 2

![image](https://github.com/user-attachments/assets/13dbe64a-1160-4fba-b185-6991bf8470bd)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/2/)

![image](https://github.com/user-attachments/assets/62c7d5f7-26af-4cfc-9e7e-c837ddf0f457)

[Realistic 2 - WebSite](https://www.hackthissite.org/missions/realistic/2/)

## Steps:

1. First we inspect the page by right-clicking on the page > click on "View page source"

![image](https://github.com/user-attachments/assets/47aacc58-88b5-4363-8e41-963649fdeda9)

2. On the page source, we can see that there is a hidden link called update: /missions/realistic/2/update.php
- We will click on it.

![image](https://github.com/user-attachments/assets/c985ce2f-accc-4044-a264-9540877c8f92)

3. The hidden link bring us to a login page.

![image](https://github.com/user-attachments/assets/0b8dd7b1-e333-479c-aca5-74ce0c999c01)

4. We will use SQLi to bypass the login page.
- Most basic SQLi = `' OR 1=1 --`

Explanation:

`' OR 1=1 --`
- `'` (Single Quote): Used to close an open string in SQL. If the input is improperly sanitized, it can terminate the intended SQL string.
- `OR 1=1`: Logical condition that always evalutes to true. This part of the injection makes the whole condition  true regardless of the actual data in the database.
- `--` (Double Hyphen): Comment indicator in SQL. Everything after `--` is ignored by SQL engine.

![image](https://github.com/user-attachments/assets/0f5e4bb4-da20-413a-88a7-2d36944924f7)

5. Since it ignores everything after --, we don't have to put anything on the password box and just hit submit and finish the challenge.

#

# Realistic Level 3

![image](https://github.com/user-attachments/assets/90735a53-1f7b-4b53-ad6d-c53f5f3ef1ef)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/3/)

![image](https://github.com/user-attachments/assets/162776be-99bc-48e8-b2aa-0cd2d7ad6f7b)

[Realistic 3 - WebSite](https://www.hackthissite.org/missions/realistic/3/)

## Steps:

1. If we Inspect on the website, we can see the comment: 

`<!--Note to the webmasterThis website has been hacked, but not totally destroyed. The old website is still up. I simply copied the old index.html file to oldindex.html and remade this one. Sorry about the inconvenience.-->`


- Right-Click on the website > Click on "Inspect".

![image](https://github.com/user-attachments/assets/da41832f-524b-4719-8866-01cc7f4277cd)

- Inspect element have comment start with: "<!--...-->"

![image](https://github.com/user-attachments/assets/e5d359f8-3b70-4284-8468-296ae89003b5)


2. We found out that there is a file call "oldindex.html" that is created by copying the original "index.html" file.

- Type in the URL: `https://www.hackthissite.org/missions/realistic/3/oldindex.html`

![image](https://github.com/user-attachments/assets/c6a36621-615b-44ca-98e9-0d9a8ab2192a)

3. We will now look at the website to see what kind of stuff we can do with it.

- There are two button in the original web page: "Read The Poetry" and "Submit Poetry".

4. Looking at Read the Poetry: We can click on the poem and read it.

![image](https://github.com/user-attachments/assets/34d51647-266a-4cbc-ad3c-4367c65b6b51)

- Clicking on Hacker, we can see the URL: `https://www.hackthissite.org/missions/realistic/3/readpoem.php?name=Hacker`

![image](https://github.com/user-attachments/assets/8a0e099e-894a-4d00-98cf-2e7d7a8b1be7)

- If we play around with the URL like deleting `?name=Hacker`: `https://www.hackthissite.org/missions/realistic/3/readpoem.php`, it will say: "You must enter a file"

![image](https://github.com/user-attachments/assets/42a42d3f-d99d-45d7-9a9a-8bc473fefeac)

URL explanation:

- `https://www.hackthissite.org/`: The domain of the website.
- `missions/realistic/3/readpoem.php`: The path to the PHP script on the server.
- `?name`: The query string, where name is a parameter key.
- `=Hacker`: Name of the parameter or the file: Hacker


5. Look at Submit Poetry: We can write the name of the poem and the details of the poem then click on the "add poem" button. And it will be uploaded to the website.
  - Note: Poems will be stored online immediately but will "not" be listed on the main poetry page until someone look at it.

![image](https://github.com/user-attachments/assets/3f7df8b7-4fd9-4a69-afbe-31de70a7ffad)

6. I will try to add a poem to see what it does:

![image](https://github.com/user-attachments/assets/20d4ee25-99c3-465a-ad0a-aa33e19f4007)

- Result: `Your poem was successfully added. Thank you for your contributions`
  - URL: https://www.hackthissite.org/missions/realistic/3/submitpoems2.php
 
![image](https://github.com/user-attachments/assets/636f1a16-a875-4911-814f-9f7e5288d097)

7. Now we have some clues that we can store a file on the website, which we can use the whole entire "oldindex.html" and replace the new "index.html".

- We will right click and "view page source" on the oldindex.html page.

![image](https://github.com/user-attachments/assets/4640f1c2-88fb-4af8-be3e-2241f8bc2487)

- Check the box for "Line wrap" > Copy the entire code. 

![image](https://github.com/user-attachments/assets/2720bb33-4ffa-4c98-bd11-0d35b5fc2649)


8. Go to Submit Poem page in order to replace the new "index.html" with "oldindex.html":

- Paste the entire thing on the Poem:

![image](https://github.com/user-attachments/assets/e319f1a5-9ab4-48b0-b88f-a4bb05f03f30)

- For the Name of the poem we have to put `../index.html` because that's where index.html is stored.

![image](https://github.com/user-attachments/assets/2efef160-134e-4fa2-89c6-ce366a111b61)


9. Click on add poem and finish the challenge.

#

# Realistic Level 4

![image](https://github.com/user-attachments/assets/855eb8ee-b0d2-4b64-ac79-01c023148fac)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/4/)

![image](https://github.com/user-attachments/assets/dd329a6f-e241-46fd-b085-757afb7f6252)

[Realistic 5 - WebSite](https://www.hackthissite.org/missions/realistic/4/)

## Steps:

1. By looking at the website URL of the products, I noticed it's SQL because of `products.php?category=1` at the end.

![image](https://github.com/user-attachments/assets/a3549bd1-f50a-4a5c-b332-5a212d4d37de)

2. I will try to use SQL injection: `UNION ALL SELECT NULL, *, NULL, NULL FROM email;` to get all the email.

Explanation:
- `UNION ALL`: The UNION ALL operator is used to combine the results of two or more SELECT statements. Unlike UNION, which removes duplicate rows, UNION ALL includes all duplicates. In SQL Injection, UNION ALL is often used to combine the results of the original query with another query specified by the attacker.
- `SELECT NULL, *, NULL, NULL`: This is the second SELECT statement being combined with the original query. The columns specified in this SELECT statement need to match the number and types of columns in the original query.
  - NULL is a placeholder that signifies no value.
  - `*` is a wildcard that selects all columns from the specified table (in this case, email).
  - The entire statement selects a total of four columns: NULL, all columns from the email table, NULL, and another NULL.
- FROM email: This specifies the table from which to select the columns. Here, the table is named email.

![image](https://github.com/user-attachments/assets/f1e0c6a0-0350-4b87-8cab-ee169230cb77)

3. We can scroll down and see the list of emails with this SQL injection:

![image](https://github.com/user-attachments/assets/9b2462ba-c3cd-4f40-a46c-29d4bbf2a445)


4. Now head to: https://www.hackthissite.org/pages/messages/msys/

- Click on Compose

![image](https://github.com/user-attachments/assets/12ebcbfa-eab4-46c6-a601-03afed110d46)


5. Send all the email to SaveTheWhales:

![image](https://github.com/user-attachments/assets/5284d1b8-704a-4c98-b7ef-e13fc27fd6f8)

6. Click on send and finish the challenge.

#

# Realistic Level 5

![image](https://github.com/user-attachments/assets/2a0daef6-0e09-4c77-817e-9eaae18ede8c)

Start on: [Direct Link](https://www.hackthissite.org/playlevel/5/)

![image](https://github.com/user-attachments/assets/c9e7c9bd-3b6c-4699-905a-7214c006bcf8)

[Realistic 5 - WebSite](https://www.hackthissite.org/missions/realistic/5/)

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

![image](https://github.com/user-attachments/assets/9fef7dd7-0c5e-467e-80c7-746c814f356d)

[Realistic 6 - WebSite](https://www.hackthissite.org/missions/realistic/6/)

![image](https://github.com/user-attachments/assets/2e815b1d-f56c-4c74-a6a6-445cc3c0e651)

## Steps:

1. I used this site to decrypt: https://telmo.pt/xecryption/

![image](https://github.com/user-attachments/assets/f9a40c01-4f29-4f97-9420-532fdd2fc314)

2. Result: 

- Samuel Smith

Thank you for looking the other way on the increased levels of toxic chemicals in the river running alongside our industrial facilities. You can pick up your payment of $20,000 in the mailbox at the mansion on the corner of 53 and St. Charles tomorrow between the hours of 3:00am and 5:00am.

Thank you,

John Sculley
ToxiCo Industrial Chemicals

![image](https://github.com/user-attachments/assets/6368394b-0af9-41e8-a993-188acd3ecb76)

3. Send the decrypted message back to ToxiCo_Watch

![image](https://github.com/user-attachments/assets/bd497298-b3d8-4bee-b403-23d84c713dbb)

4. Click on Send and finish the challenge.

#

# Realistic Level 7 

view-source:https://www.hackthissite.org/missions/realistic/7/showimages.php?file=/images/admin/.htpasswd



# Key Takeaway:

## 1. We can tamper the score of an element by going into inspect element.

## 2. Most basic SQL injection: `' OR 1=1 --`

## 3. We can take advantage of php paths such as: `?name=Hacker`

## 4. SQLi: `UNION ALL SELECT NULL, *, NULL, NULL FROM email;`

## 5. /robots.txt; john --format=RAW-md4 [file]; we can use --show on john to show cracked password from before. 
