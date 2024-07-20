# Realistic Level 1

![image](https://github.com/user-attachments/assets/707e64a4-af3e-4623-85d7-5e31c42f213b)

Start off on: [Direct Link](https://www.hackthissite.org/playlevel/1/)

![image](https://github.com/user-attachments/assets/b8a49a19-4ede-41b9-88ad-4218f167bf8d)

[Site](https://www.hackthissite.org/missions/realistic/1/)

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

Start off on: [Direct Link](https://www.hackthissite.org/playlevel/2/)

![image](https://github.com/user-attachments/assets/62c7d5f7-26af-4cfc-9e7e-c837ddf0f457)

[Site](https://www.hackthissite.org/missions/realistic/2/)

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



# Key Takeaway:

## 1. We can tamper the score of an element by going into inspect element.

## 2. Most basic SQL injection: `' OR 1=1 --`
