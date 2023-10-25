# Task 11  [Severity 3] Sensitive Data Exposure (Challenge)

Copy the IP from the of the active machine on Tryhackme and paste it into the attackbox browser.

<p align="center">
<br/>
<img src="https://i.imgur.com/7ZX95Tf.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

1. What is the name of the mentioned directory?

Hint: Have a look at the source code on the /login page.

- Click on "Login"

<p align="center">
<br/>
<img src="https://i.imgur.com/HPpTGvy.png" height="90%" width="90%" alt=""/>
<br />

- Right-click on the login page and click on "View Page Source".

<p align="center">
<br/>
<img src="https://i.imgur.com/gKPJqpo.png" height="90%" width="90%" alt=""/>
<br />

- In the Page Source. Colored in green `/asset`.

<p align="center">
<br/>
<img src="https://i.imgur.com/lVqSwNB.png" height="90%" width="90%" alt=""/>
<br />

Answer: `/asset`


<h2></h2>

2. Navigate to the directory you found in question one. What file stands out as being likely to contain sensitive data?

- On the browser, navigate to the directory: "http://10.10.220.142/assets/".

<p align="center">
<br/>
<img src="https://i.imgur.com/pFUaLih.png" height="90%" width="90%" alt=""/>
<br />

- On the directory, "webapp.db" seems to be the flat-file database. Which is likely to contain sensitive data.

<p align="center">
<br/>
<img src="https://i.imgur.com/2XzLtkF.png" height="90%" width="90%" alt=""/>
<br />

Answer: `webapp.db`

<h2></h2>

3. Use the supporting material to access the sensitive data. What is the password hash of the admin user?

- Download the "webapp.db" by clicking on it.

<p align="center">
<br/>
<img src="https://i.imgur.com/EqH7Zlx.png" height="90%" width="90%" alt=""/>
<br />

- Open Terminal.
  - Type in: `Sqlite3 webapp.db`
  - The command sqlite3 webapp.db is used to interact with an SQLite database named "webapp.db" using the SQLite command-line interface (CLI) tool.

<p align="center">
<br/>
<img src="https://i.imgur.com/wFNsrfN.png" height="90%" width="90%" alt=""/>
<br />

- Type in: `.tables`
  - `.tables` command to list all the tables in the current database.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/twncji9.png" height="90%" width="90%" alt=""/>
<br />

- Type in: PRAGMA table_info(users);
  - In SQLite, the PRAGMA table_info(table_name) statement is used to retrieve information about the columns (fields) of a specific table in a database.
  - PRAGMA: This is a special command used to query or set various SQLite library parameters.
  - table_info(table_name): This is the argument provided to the PRAGMA command. You replace table_name with the name of the table you want to retrieve information about.

<p align="center">
<br/>
<img src="https://i.imgur.com/H7TsZhR.png" height="90%" width="90%" alt=""/>
<br />
 
- Type in: SELECT * FROM users;
  - In SQLite, the SELECT * FROM users; statement is an SQL query used to retrieve all records (rows) from the "users" table in a database. Here's a breakdown of this SQL statement:
  - SELECT: This is the SQL keyword used to retrieve data from a table or view.
  - *: The asterisk * is a wildcard character used to represent all columns in the table. In this context, it means you want to retrieve all columns for each row.
  - FROM: This is another SQL keyword used to specify the source of the data you want to retrieve. In this case, it specifies the "users" table as the source.
  - users: This is the name of the table you want to retrieve data from.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/bJ3LT73.png" height="90%" width="90%" alt=""/>
<br />

Answer: `6eea9b7ef19179a06954edd0f6c05ceb`


<h2></h2>


4. Crack the hash.
    What is the admin's plaintext password?

- Copy the hash for admin and to go Crackstation and paste it there and try to crack the hash.

<p align="center">
<br/>
<img src="https://i.imgur.com/EKIBdM9.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/kojrPcK.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/QLcPIQO.png" height="90%" width="90%" alt=""/>
<br />

Answer: `qwertyuiop`

<h2></h2>

5. Login as the admin. What is the flag?

- Head back to the login page for http://10.10.220.142/
  - Enter in: Username: `admin`; Password: `qwertyuiop`

<p align="center">
<br/>
<img src="https://i.imgur.com/pyHTWnN.png" height="90%" width="90%" alt=""/>
<br />

- Successfully captured the flag.

<p align="center">
<br/>
<img src="https://i.imgur.com/cdyocnH.png" height="90%" width="90%" alt=""/>
<br />

Answer: THM{Yzc2YjdkMjE5N2VjMzNhOTE3NjdiMjdl}
