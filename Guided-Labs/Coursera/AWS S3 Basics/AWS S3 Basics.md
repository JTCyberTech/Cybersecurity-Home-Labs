# AWS S3 Basics

<h2>Task 1: Creating my first AWS S3 Bucket</h2>

<h3>Key Takeaways </h3>

- S3: Simple Storage Service.
- S3 buckets are containers and anything stored in it is called "Objects".
- S3 buckets name has to be unique globally.

<h2></h2>

- Login to AWS Management console: Click [Here](https://aws.amazon.com/console/).

- For a guide to create an account on AWS: Click [Here](https://github.com/jefftsui1/Cybersecurity-Home-Labs/blob/main/Guided-Labs/Ethical%20Hacking/AWS%20Home%20Lab/1.%20Sign%20Up%20for%20AWS%20and%20Enable%20MFA%20Security.md).

<p align="center">
<br/>
<img src="https://i.imgur.com/gxd8hzm.png" height="90%" width="90%" alt=""/>
<br />

- Navigate to the S3 service.
  - On the search bar, search "S3" and click on it.

<p align="center">
<br/>
<img src="https://i.imgur.com/IyhUK5x.png" height="90%" width="90%" alt=""/>
<br />

- On the Amazon S3 dashboard, click on "Create bucket".

<p align="center">
<br/>
<img src="https://i.imgur.com/gZyt2QK.png" height="90%" width="90%" alt=""/>
<br />

- On the Create bucket page:
  - For Bucket name: (put in a global unique name).


<p align="center">
<br/>
<img src="https://i.imgur.com/ujXPSRO.png" height="90%" width="90%" alt=""/>
<br />
 
- Scroll down on the Create bucket page:
  - For "Block Public Access setting for this bucket".
     - Unchecking this will grant S3 bucket access to the internet.
     - Keep it as check for now.

<p align="center">
<br/>
<img src="https://i.imgur.com/N79bQWX.png" height="90%" width="90%" alt=""/>
<br />

- Scroll down on the Create bucket page: 
   - For "Bucket Versioning".
     - We can enaable versioning by clicking on "Enable".
     - Bucket versioning provides a robust and secure way to preserve and retrieve prior versions of objects, enhancing data durability and aiding in data recovery and compliance.
     - Keep it as "Disable" for now.
    
<p align="center">
<br/>
<img src="https://i.imgur.com/7n2Ofvx.png" height="90%" width="90%" alt=""/>
<br />
      
- Scroll down on the Create bucket page:
  - For "Tags".
    - Tags are defined by the user and can help us track the project cost.
    - Create tag by: "Add tag".
      - Key: "Project"; Value: "Basics".
     
<p align="center">
<br/>
<img src="https://i.imgur.com/1NgmhBj.png" height="90%" width="90%" alt=""/>
<br />


- Scroll down on the Create bucket page:
  - For "Default encryption".
    - Encryption type: "Server-side encryption with Amazon S3 managed keys (SSE-S3)".
    - Bucket key: "Disable".
   
<p align="center">
<br/>
<img src="https://i.imgur.com/UGI2IwG.png" height="90%" width="90%" alt=""/>
<br />


- Click on "Create bucket" on the bottom of the page.

<p align="center">
<br/>
<img src="https://i.imgur.com/wyqZsgr.png" height="90%" width="90%" alt=""/>
<br />

- Successfully created the S3 Bucket.

<p align="center">
<br/>
<img src="https://i.imgur.com/NBzY5z7.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h2>Task 2: Upload Content to S3 Bucket</h2>


<h3>Key Takeaways</h3>

- Upload objects to the S3 bucket.
- Manage S3 bucket using policy and ACL.

<h2></h2>

<h3>Creating Two Folders in the Bucket</h3>

- Navigate into the bucket by clicking on the name.

<p align="center">
<br/>
<img src="https://i.imgur.com/NBzY5z7.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Create folder". Create two folders. One for images and other one for text file.

<p align="center">
<br/>
<img src="https://i.imgur.com/xDb1phR.png" height="90%" width="90%" alt=""/>
<br />

- Name the first folder "Images". "Do not specify an encryption key" for Server-side encryption. Then, click on "Create folder".

<p align="center">
<br/>
<img src="https://i.imgur.com/ZlXCNBr.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Create folder" to create the text file.

<p align="center">
<br/>
<img src="https://i.imgur.com/jOMcDa1.png" height="90%" width="90%" alt=""/>
<br />

- Name the second folder "Text". "Do not specify an encryption key" for Server-side encryption. Then, click on "Create folder".

<p align="center">
<br/>
<img src="https://i.imgur.com/EHlADlK.png" height="90%" width="90%" alt=""/>
<br />

- Both folders are created successfully.

<p align="center">
<br/>
<img src="https://i.imgur.com/paPyYNf.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Upload Images in the Images Folder</h3>

- Click on the "Images Folder".

<p align="center">
<br/>
<img src="https://i.imgur.com/T1OlLnd.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Upload".

<p align="center">
<br/>
<img src="https://i.imgur.com/ZtWqS1j.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Add files".
